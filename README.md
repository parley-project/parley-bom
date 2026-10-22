# parley-bom

The bill of materials (BOM) for **Parley**, a family of Java libraries for implementing internet
protocols. It lists versions of the Parley modules that work together, so you can use several of
them without picking a version for each.

## Using it

Import the BOM once, then add Parley modules without versions:

```xml
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>us.bringardner.parley</groupId>
            <artifactId>parley-bom</artifactId>
            <version>2.0.0</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>

<dependencies>
    <dependency>
        <groupId>us.bringardner.parley</groupId>
        <artifactId>parley-ftp</artifactId>
    </dependency>
    <dependency>
        <groupId>us.bringardner.parley</groupId>
        <artifactId>parley-dns</artifactId>
    </dependency>
</dependencies>
```

Modules a Parley module brings in (parley-core, parley-net, ...) also get the BOM's versions.

## What it covers

parley-core, parley-brand, parley-io, parley-net, parley-files, parley-files-ftp, parley-files-sftp,
parley-files-sftp-jsch, parley-files-sftp-mina, parley-files-sftp-parley-ssh, parley-files-jdbc,
parley-files-swing, parley-files-fx, parley-credentials-keychain, parley-ftp, parley-dns, parley-ssh,
parley-mail, parley-smtp, parley-imap, parley-pop3, parley-dap and parley-loupe, plus the widget
libraries bringardner-swing-widgets and bringardner-fx-widgets.
It lists only Parley's own artifacts, never third-party ones.

## Maintaining it

Starting with 2.0.0, all Parley modules share one version, set in parley-parent. The BOM has the
same version and lists every Parley module at `${project.version}`, so there is nothing to update per
module. Release the BOM along with the modules.
