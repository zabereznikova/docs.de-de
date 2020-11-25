---
title: Kompatibilität und Migration von Richtlinien für die Codezugriffssicherheit
description: Lesen Sie eine Zusammenfassung, und sehen Sie sich die Links zur Kompatibilität und Migration der Code Zugriffssicherheit in .NET Framework 4 an.
ms.date: 03/30/2017
helpviewer_keywords:
- policy migration, compatibility
- CLR policy migration
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
ms.openlocfilehash: 389976556175c0b6b300e75d01327d91f94f0db9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733385"
---
# <a name="code-access-security-policy-compatibility-and-migration"></a>Kompatibilität und Migration von Richtlinien für die Codezugriffssicherheit

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

Der Richtlinien Teil der Code Zugriffssicherheit (Code Access Security, CAS) wurde in der .NET Framework 4 als veraltet eingestuft. Daher können Kompilierungs Warnungen und Lauf Zeit Ausnahmen auftreten, wenn Sie die veralteten Richtlinien Typen und Member [explizit](#explicit_use) oder [implizit](#implicit_use) (über andere Typen und Member) aufzurufen.

Sie können die Warnungen und Fehler folgendermaßen vermeiden:

- [Migrieren](#migration) zu den .NET Framework 4-Ersetzungen für die veralteten Aufrufe.

   \- oder -

- Verwenden des- [ \<NetFx40_LegacySecurityPolicy> Konfigurations Elements](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) , um das Legacy-CAS-Richtlinien Verhalten zu abonnieren.

Dieses Thema enthält folgende Abschnitte:

- [Explizite Verwendung](#explicit_use)

- [Implizite Verwendung](#implicit_use)

- [Fehler und Warnungen](#errors_and_warnings)

- [Migration: Ersatz für veraltete Aufrufe](#migration)

- [Kompatibilität: Verwenden der CAS-Legacyrichtlinienoption](#compatibility)

<a name="explicit_use"></a>

## <a name="explicit-use"></a>Explizite Verwendung

Elemente, die die Sicherheitsrichtlinie direkt bearbeiten oder die CAS-Richtlinie für den Sandkasten benötigen, sind veraltet und generieren standardmäßig Fehler.

Im Folgenden sind Beispiele dafür aufgeführt:

- <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.HostSecurityManager.DomainPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolveSystemPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolvePolicyGroups%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.PolicyHierarchy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.SavePolicy%2A?displayProperty=nameWithType>

<a name="implicit_use"></a>

## <a name="implicit-use"></a>Implizite Verwendung

Mehrere Überladungen beim Laden einer Assembly generieren Fehler aufgrund ihrer impliziten Verwendung der CAS-Richtlinie. Diese Überladungen nehmen einen Parameter <xref:System.Security.Policy.Evidence> an, der verwendet wird, um die CAS-Richtlinie aufzulösen und einen Berechtigungssatz für eine Assembly bereitzustellen.

Beispiele: Die veralteten Überladungen sind die Überladungen, die <xref:System.Security.Policy.Evidence> als Parameter annehmen:

- <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

<a name="errors_and_warnings"></a>

## <a name="errors-and-warnings"></a>Fehler und Warnungen

Die veralteten Typen und Elemente generieren die folgenden Fehlermeldungen, wenn sie verwendet werden. Beachten Sie, dass der Typ <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> selbst nicht veraltet ist.

Warnung zur Kompilierzeit:

`warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework. Please use <suggested alternate API>. See <link> for more information.'`

Laufzeitausnahme:

<xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`

<a name="migration"></a>

## <a name="migration-replacement-for-obsolete-calls"></a>Migration: Ersatz für veraltete Aufrufe

### <a name="determining-an-assemblys-trust-level"></a>Bestimmen der Vertrauensebene einer Assembly

Die CAS-Richtlinie wird häufig verwendet, um den Berechtigungssatz einer Assembly oder Anwendungsdomäne oder die Vertrauensebene zu bestimmen. Der .NET Framework 4 macht die folgenden nützlichen Eigenschaften verfügbar, die nicht zum Auflösen von Sicherheitsrichtlinien erforderlich sind:

- <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=nameWithType>

### <a name="application-domain-sandboxing"></a>Sandkasten für Anwendungsdomänen

Die Methode <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> wird in der Regel verwendet, um Assemblys in einer Anwendungsdomäne in einem Sandkasten auszuführen. Der .NET Framework 4 macht Mitglieder verfügbar, die für diesen Zweck nicht verwendet werden müssen <xref:System.Security.Policy.PolicyLevel> . Weitere Informationen finden Sie unter Gewusst [wie: Ausführen von teilweise vertrauenswürdigem Code in einem Sandkasten](how-to-run-partially-trusted-code-in-a-sandbox.md).

### <a name="determining-a-safe-or-reasonable-permission-set-for-partially-trusted-code"></a>Bestimmen eines sicheren oder geeigneten Berechtigungssatzes für teilweise vertrauenswürdigen Code

Hosts müssen häufig die Berechtigungen ermitteln, die für das Ausführen von gehostetem Code in einem Sandkasten geeignet sind. Vor der .NET Framework 4 bot die CAS-Richtlinie eine Möglichkeit, dies mit der-Methode durchzuführen <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> . Als Ersatz stellt .NET Framework 4 die- <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> Methode bereit, die einen sicheren Standard Berechtigungs Satz für den bereitgestellten Beweis zurückgibt.

### <a name="non-sandboxing-scenarios-overloads-for-assembly-loads"></a>Szenarien ohne Sandkasten: Überladungen für das Laden von Assemblys

Der Grund für die Verwendung einer Überladung für das Laden einer Assembly kann die Verwendung von Parametern sein, die andernfalls nicht verfügbar sind, anstatt die Assembly in einem Sandkastens auszuführen. Beginnend mit dem .NET Framework 4 werden bei assemblylastenüberladungen, die kein- <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> Objekt als Parameter benötigen, z <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType> . b., dieses Szenario aktiviert.

Wenn Sie einen Sandkasten für eine Assembly verwenden möchten, verwenden Sie die <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType>-Überladung.

<a name="compatibility"></a>

## <a name="compatibility-using-the-cas-policy-legacy-option"></a>Kompatibilität: Verwenden der CAS-Legacyrichtlinienoption

Mithilfe des [ \<NetFx40_LegacySecurityPolicy> Konfigurations Elements](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) können Sie angeben, dass ein Prozess oder eine Bibliothek eine Legacy-CAS-Richtlinie verwendet. Wenn Sie dieses Element aktivieren, funktionieren die Richtlinien- und Beweisüberladungen wie in früheren Versionen des Frameworks.

> [!NOTE]
> Das CAS-Richtlinienverhalten wird auf der Grundlage einer Laufzeitversion angegeben. Das Ändern der CAS-Richtlinie für eine Laufzeitversion besitzt daher keine Auswirkungen auf die CAS-Richtlinie einer anderen Version.

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Weitere Informationen

- [How to: Ausführen von teilweise vertrauenswürdigem Code in einem Sandkasten](how-to-run-partially-trusted-code-in-a-sandbox.md)
- [Richtlinien für das Schreiben von sicherem Code](../../standard/security/secure-coding-guidelines.md)
