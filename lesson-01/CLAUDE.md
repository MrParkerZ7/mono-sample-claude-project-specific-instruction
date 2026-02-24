# CLAUDE.md - DrawIO Cloud Architecture Diagram Guidelines

## Overview
When creating `.drawio` files for cloud architecture diagrams, always use the correct shape library icons for each cloud provider. DrawIO uses XML format with specific style attributes to reference official cloud service shapes.

## File Structure
DrawIO files are XML-based with this basic structure:
```xml
<mxfile host="app.diagrams.net">
  <diagram name="Page-1" id="...">
    <mxGraphModel>
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <!-- Your shapes go here -->
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

---

## CRITICAL: Parent-Child Relationships for Grouping

**For elements to move together when dragging a group container, child elements MUST have their `parent` attribute set to the container's ID.**

### How It Works
- `parent="0"` - The root cell (id="0")
- `parent="1"` - Direct child of the diagram root (top-level elements)
- `parent="<container-id>"` - Child of a specific container (moves with container)

### Hierarchy Example
```
AWS Cloud (parent="1")
  └── Region (parent="aws-cloud")
        └── VPC (parent="region")
              ├── Public Subnet (parent="vpc")
              │     ├── IGW (parent="public-subnet")
              │     └── ALB (parent="public-subnet")
              └── Private Subnet (parent="vpc")
                    ├── ECS (parent="private-subnet")
                    └── RDS (parent="private-subnet")
```

### Coordinate System
**IMPORTANT:** When an element has a parent container, its `x` and `y` coordinates are **relative to the parent's top-left corner**, not the diagram origin.

```xml
<!-- Container at absolute position (200, 100) -->
<mxCell id="vpc" parent="1" ...>
  <mxGeometry x="200" y="100" width="400" height="300"/>
</mxCell>

<!-- Child at (20, 40) RELATIVE to VPC = absolute (220, 140) -->
<mxCell id="ecs" parent="vpc" ...>
  <mxGeometry x="20" y="40" width="60" height="60"/>
</mxCell>
```

### Nesting Rules
1. **Groups must be defined BEFORE their children** in the XML
2. **Edges (connections) should have `parent="1"`** - they connect across containers
3. **Use relative coordinates** for children inside containers
4. **Container must have `vertex="1"`** to be a valid parent

---

## AWS Shape References

Use `shape=mxgraph.aws4.` prefix for AWS Architecture 2024 icons.

### Compute
| Service | Shape Style |
|---------|-------------|
| EC2 | `shape=mxgraph.aws4.ec2` |
| Lambda | `shape=mxgraph.aws4.lambda_function` |
| ECS | `shape=mxgraph.aws4.ecs` |
| EKS | `shape=mxgraph.aws4.eks` |
| Fargate | `shape=mxgraph.aws4.fargate` |
| Elastic Beanstalk | `shape=mxgraph.aws4.elastic_beanstalk` |

### Storage
| Service | Shape Style |
|---------|-------------|
| S3 | `shape=mxgraph.aws4.s3` |
| EBS | `shape=mxgraph.aws4.elastic_block_store` |
| EFS | `shape=mxgraph.aws4.elastic_file_system` |
| Glacier | `shape=mxgraph.aws4.glacier` |

### Database
| Service | Shape Style |
|---------|-------------|
| RDS | `shape=mxgraph.aws4.rds` |
| DynamoDB | `shape=mxgraph.aws4.dynamodb` |
| Aurora | `shape=mxgraph.aws4.aurora` |
| ElastiCache | `shape=mxgraph.aws4.elasticache` |
| Redshift | `shape=mxgraph.aws4.redshift` |

### Networking
| Service | Shape Style |
|---------|-------------|
| VPC | `shape=mxgraph.aws4.vpc` |
| CloudFront | `shape=mxgraph.aws4.cloudfront` |
| Route 53 | `shape=mxgraph.aws4.route_53` |
| API Gateway | `shape=mxgraph.aws4.api_gateway` |
| ELB/ALB | `shape=mxgraph.aws4.elastic_load_balancing` |
| NAT Gateway | `shape=mxgraph.aws4.nat_gateway` |
| Internet Gateway | `shape=mxgraph.aws4.internet_gateway` |

### Security
| Service | Shape Style |
|---------|-------------|
| IAM | `shape=mxgraph.aws4.iam` |
| Cognito | `shape=mxgraph.aws4.cognito` |
| KMS | `shape=mxgraph.aws4.key_management_service` |
| WAF | `shape=mxgraph.aws4.waf` |
| Secrets Manager | `shape=mxgraph.aws4.secrets_manager` |

### Messaging & Integration
| Service | Shape Style |
|---------|-------------|
| SQS | `shape=mxgraph.aws4.sqs` |
| SNS | `shape=mxgraph.aws4.sns` |
| EventBridge | `shape=mxgraph.aws4.eventbridge` |
| Step Functions | `shape=mxgraph.aws4.step_functions` |

### Monitoring
| Service | Shape Style |
|---------|-------------|
| CloudWatch | `shape=mxgraph.aws4.cloudwatch` |
| X-Ray | `shape=mxgraph.aws4.xray` |

### AWS Groups (for VPC, Subnets, etc.)
| Group Type | Shape Style |
|------------|-------------|
| AWS Cloud | `shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_aws_cloud` |
| Region | `shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_region` |
| VPC | `shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_vpc` |
| Availability Zone | `shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_availability_zone` |
| Public Subnet | `shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_security_group` (green) |
| Private Subnet | `shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_security_group` (blue) |

---

## Azure Shape References

Use `shape=mxgraph.azure.` prefix for Azure icons.

### Compute
| Service | Shape Style |
|---------|-------------|
| Virtual Machine | `shape=mxgraph.azure.compute.virtual_machine` |
| App Service | `shape=mxgraph.azure.compute.app_services` |
| Functions | `shape=mxgraph.azure.compute.function_apps` |
| AKS | `shape=mxgraph.azure.compute.kubernetes_services` |
| Container Instances | `shape=mxgraph.azure.compute.container_instances` |

### Storage
| Service | Shape Style |
|---------|-------------|
| Blob Storage | `shape=mxgraph.azure.storage.blob_block` |
| Storage Account | `shape=mxgraph.azure.storage.storage_accounts` |
| Disk | `shape=mxgraph.azure.storage.disks` |

### Database
| Service | Shape Style |
|---------|-------------|
| SQL Database | `shape=mxgraph.azure.databases.sql_databases` |
| Cosmos DB | `shape=mxgraph.azure.databases.azure_cosmos_db` |
| Redis Cache | `shape=mxgraph.azure.databases.cache_redis` |

### Networking
| Service | Shape Style |
|---------|-------------|
| Virtual Network | `shape=mxgraph.azure.networking.virtual_networks` |
| Load Balancer | `shape=mxgraph.azure.networking.load_balancers` |
| Application Gateway | `shape=mxgraph.azure.networking.application_gateways` |
| CDN | `shape=mxgraph.azure.networking.cdn_profiles` |
| DNS Zone | `shape=mxgraph.azure.networking.dns_zones` |

### Security
| Service | Shape Style |
|---------|-------------|
| Key Vault | `shape=mxgraph.azure.security.key_vaults` |
| Azure AD | `shape=mxgraph.azure.identity.azure_active_directory` |

---

## Kubernetes Shape References

Use `shape=mxgraph.kubernetes.` prefix for Kubernetes icons.

| Resource | Shape Style |
|----------|-------------|
| Pod | `shape=mxgraph.kubernetes.pod` |
| Deployment | `shape=mxgraph.kubernetes.deploy` |
| Service | `shape=mxgraph.kubernetes.svc` |
| Ingress | `shape=mxgraph.kubernetes.ing` |
| ConfigMap | `shape=mxgraph.kubernetes.cm` |
| Secret | `shape=mxgraph.kubernetes.secret` |
| PersistentVolume | `shape=mxgraph.kubernetes.pv` |
| PersistentVolumeClaim | `shape=mxgraph.kubernetes.pvc` |
| StatefulSet | `shape=mxgraph.kubernetes.sts` |
| DaemonSet | `shape=mxgraph.kubernetes.ds` |
| ReplicaSet | `shape=mxgraph.kubernetes.rs` |
| Namespace | `shape=mxgraph.kubernetes.ns` |
| Node | `shape=mxgraph.kubernetes.node` |
| Cluster | `shape=mxgraph.kubernetes.control_plane` |

---

## Example: AWS ECS Architecture Cell

```xml
<mxCell id="ecs-1" value="ECS Cluster"
  style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=none;strokeColor=#ffffff;fillColor=#ED7100;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.ecs;labelBackgroundColor=none;"
  vertex="1" parent="1">
  <mxGeometry x="200" y="150" width="78" height="78" as="geometry"/>
</mxCell>
```

## Example: Complete AWS Architecture Snippet (with proper nesting)

```xml
<mxfile host="app.diagrams.net" modified="2024-01-01T00:00:00.000Z" agent="Claude">
  <diagram name="AWS-Architecture" id="aws-arch-1">
    <mxGraphModel dx="1200" dy="800" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="850" pageHeight="1100">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>

        <!-- VPC Group (top-level, parent="1") -->
        <mxCell id="vpc-group" value="VPC" style="sketch=0;outlineConnect=0;gradientColor=none;html=1;whiteSpace=wrap;fontSize=12;fontStyle=0;shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_vpc;strokeColor=#248814;fillColor=none;verticalAlign=top;align=left;spacingLeft=30;fontColor=#248814;dashed=0;" vertex="1" parent="1">
          <mxGeometry x="40" y="40" width="400" height="300" as="geometry"/>
        </mxCell>

        <!-- ECS Service (INSIDE VPC: parent="vpc-group", coords relative to VPC) -->
        <mxCell id="ecs-1" value="ECS" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.ecs;" vertex="1" parent="vpc-group">
          <mxGeometry x="40" y="80" width="60" height="60" as="geometry"/>
        </mxCell>

        <!-- RDS Database (INSIDE VPC: parent="vpc-group", coords relative to VPC) -->
        <mxCell id="rds-1" value="RDS" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#C925D1;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.rds;" vertex="1" parent="vpc-group">
          <mxGeometry x="200" y="80" width="60" height="60" as="geometry"/>
        </mxCell>

        <!-- Connection Arrow (parent="1" - edges stay at root level) -->
        <mxCell id="edge-1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeColor=#232F3E;strokeWidth=2;" edge="1" parent="1" source="ecs-1" target="rds-1">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>

      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

**Key points in this example:**
- `vpc-group` has `parent="1"` (top-level container)
- `ecs-1` and `rds-1` have `parent="vpc-group"` (nested inside VPC)
- Coordinates for ECS/RDS are relative to VPC's top-left corner
- Edge `parent="1"` keeps connections at root level for proper rendering

---

## Style Guidelines

### Common Style Attributes
- `sketch=0` - Clean lines (not hand-drawn)
- `outlineConnect=0` - Connection points at shape edge
- `aspect=fixed` - Maintain aspect ratio
- `verticalLabelPosition=bottom` - Label below icon
- `verticalAlign=top` - Align icon to top
- `html=1` - Enable HTML in labels

### AWS Color Palette
| Category | Fill Color |
|----------|------------|
| Compute (Orange) | `#ED7100` |
| Storage (Green) | `#7AA116` |
| Database (Purple) | `#C925D1` |
| Networking (Purple) | `#8C4FFF` |
| Security (Red) | `#DD344C` |
| Analytics (Blue) | `#006Fà7` |

### Recommended Icon Size
- Standard icons: `60x60` or `78x78`
- Group containers: Scale based on content
- Minimum spacing between icons: `40px`

---

## Instructions for Claude

1. **Always use official shape references** - Never use generic rectangles for cloud services
2. **Match provider to request** - If user says "AWS diagram", use `mxgraph.aws4.*` shapes
3. **Include proper groups** - Use VPC/Subnet/Region groups to show architecture boundaries
4. **CRITICAL: Set correct parent attributes** - Children must have `parent="<container-id>"` to move with their container
5. **Use relative coordinates for nested elements** - Child coordinates are relative to parent's top-left
6. **Define containers before children** - Parent elements must appear first in XML
7. **Keep edges at root level** - Connection edges should have `parent="1"`
8. **Add connection edges** - Show data flow with properly styled arrows
9. **Use correct colors** - Follow the provider's color palette for each service category
10. **Label all components** - Include service names in the `value` attribute
11. **Position logically** - Arrange components following left-to-right or top-to-bottom flow
