Initialize GRACE framework structure for this project.

## Steps:

1. Create the `docs/` directory with these files:

### docs/knowledge-graph.xml
Create the initial knowledge graph skeleton. Ask the user for:
- Project name and short annotation
- Main keywords (for domain activation)
- Primary language and framework
- High-level module list (if known)

Use this template:
```xml
<KnowledgeGraph>
  <Project NAME="$name" VERSION="0.1.0">
    <keywords>$keywords</keywords>
    <annotation>$annotation</annotation>

    <!-- Module declarations use unique ID-based tags:
         <M-xxx NAME="..." TYPE="...">
           <purpose>...</purpose>
           <path>...</path>
           <depends>...</depends>
         </M-xxx>
         See CLAUDE.md "Documentation Artifacts" for full convention. -->

  </Project>
</KnowledgeGraph>
```

### docs/requirements.xml
Create an empty requirements template with AAG (Actor-Action-Goal) notation:
```xml
<RequirementsAnalysis VERSION="0.1.0">
  <UseCases>
    <!-- Use cases use unique ID-based tags:
    <UC-001>
      <Actor>User</Actor>
      <Action>Does something</Action>
      <Goal>To achieve outcome</Goal>
      <AcceptanceCriteria>How we know it works</AcceptanceCriteria>
    </UC-001>
    -->
  </UseCases>
</RequirementsAnalysis>
```

### docs/technology.xml
Ask the user about their stack choices, then populate:
```xml
<TechnologyStack VERSION="0.1.0">
  <Runtime>$runtime $version</Runtime>
  <Language>$language $version</Language>
  <Framework>$framework $version</Framework>
  <!-- Add specific libraries, version constraints, and compatibility notes -->
  <VersionConstraints>
    <!-- Critical: specify exact versions to prevent AI from generating code for wrong API versions -->
  </VersionConstraints>
</TechnologyStack>
```

### docs/development-plan.xml
Create empty blueprint:
```xml
<DevelopmentPlan VERSION="0.1.0">
  <Modules>
    <!-- Modules use unique ID-based tags: <M-xxx NAME="..." TYPE="..." LAYER="N" ORDER="N">
         See CLAUDE.md "Documentation Artifacts" for full convention. -->
  </Modules>
  <DataFlow>
    <!-- Flows use unique ID-based tags: <DF-xxx NAME="..." TRIGGER="..."> -->
  </DataFlow>
  <ImplementationOrder>
    <!-- Phases use unique tags: <Phase-N name="..." status="pending"> -->
  </ImplementationOrder>
</DevelopmentPlan>
```

2. Verify that CLAUDE.md exists at project root with GRACE principles. If not — create one from the GRACE template or warn the user to add GRACE conventions.

3. Print a summary of created files and suggest the next step: "Run `/grace plan` to start the architectural planning phase."
