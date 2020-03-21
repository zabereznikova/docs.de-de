---
title: Sicherheitsaspekte bei der Reflektionsausgabe
ms.date: 03/30/2017
helpviewer_keywords:
- partially trusted code
- emitting dynamic assemblies, security
- reflection emit, security
- reflection emit, partial trust scenarios
- partial trust,emitting dynamic methods
- anonymously hosted dynamic methods [.NET Framework]
- emitting dynamic assemblies,partial trust scenarios
- dynamic assemblies, security
ms.assetid: 0f8bf8fa-b993-478f-87ab-1a1a7976d298
ms.openlocfilehash: 11eb4c9bc4ba1b1fe9051a04d12f893e693fb175
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180459"
---
# <a name="security-issues-in-reflection-emit"></a>Sicherheitsaspekte bei der Reflektionsausgabe
.NET Framework bietet drei Möglichkeiten zum Ausgeben der Microsoft Intermediate Language (MSIL), die jeweils mit eigenen Sicherheitsproblemen verbunden sind:  
  
- [Dynamische Assemblys](#Dynamic_Assemblies)  
  
- [Anonym gehostete dynamische Methoden](#Anonymously_Hosted_Dynamic_Methods)  
  
- [Vorhandenen Assemblys zugeordnete dynamische Methoden](#Dynamic_Methods_Associated_with_Existing_Assemblies)  
  
 Unabhängig davon, wie Sie dynamischen Code generieren, erfordert die Ausführung des generierten Codes alle Berechtigungen, die für die Typen und Methoden erforderlich sind, die von dem generierten Code verwendet werden.  
  
> [!NOTE]
> Die Berechtigungen, die für das Reflektieren und Ausgeben von Code erforderlich sind, haben sich mit den Nachfolgeversionen von .NET Framework geändert. Siehe weiter unten in diesem Thema unter [Versionsinformationen](#Version_Information).  
  
<a name="Dynamic_Assemblies"></a>
## <a name="dynamic-assemblies"></a>Dynamische Assemblys  
 Dynamische Assemblys werden unter Verwendung von Überladungen der <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>-Methode erstellt. Die meisten Überladungen dieser Methode werden in .NET Framework 4 nicht mehr unterstützt, weil computerweite Sicherheitsrichtlinien beseitigt wurden. (Siehe [Sicherheitsänderungen](../security/security-changes.md).) Die verbleibenden Überladungen können von jedem Code ausgeführt werden, unabhängig von der Vertrauensstufe. Diese Überladungen fallen in zwei Gruppen: solche, die eine Liste mit Attributen angeben, die auf die dynamische Assembly angewendet werden sollen, wenn sie erstellt wird, und solche, die dies unterlassen. Wenn Sie das Transparenzmodell für die Assembly beim Erstellen nicht durch Anwendung des <xref:System.Security.SecurityRulesAttribute>-Attributs angeben, wird das Transparenzmodell von der ausgebenden Assembly geerbt.  
  
> [!NOTE]
> Attribute, die Sie mithilfe von <xref:System.Reflection.Emit.AssemblyBuilder.SetCustomAttribute%2A> auf die dynamische Assembly nach deren Erstellung anwenden, werden erst wirksam, nachdem die Assembly auf dem Datenträger gespeichert und wieder in den Arbeitsspeicher geladen wurde.  
  
 Code in einer dynamischen Assembly kann auf sichtbare Typen und Member in anderen Assemblys zugreifen.  
  
> [!NOTE]
> Dynamische Assemblys verwenden nicht die Flags <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType> und <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>, die es dynamischen Methoden gestatten, auf nicht öffentliche Typen und Member zuzugreifen.  
  
 Flüchtige dynamische Assemblys werden im Arbeitsspeicher erstellt und nie auf dem Datenträger gespeichert, weshalb sie keine Berechtigungen für den Dateizugriff benötigen. Für das Speichern einer dynamischen Assembly auf dem Datenträger ist <xref:System.Security.Permissions.FileIOPermission> mit den geeigneten Flags erforderlich.  
  
### <a name="generating-dynamic-assemblies-from-partially-trusted-code"></a>Generieren von dynamischen Assemblys aus teilweise vertrauenswürdigem Code  
 Beachten Sie die Bedingungen, unter denen eine Assembly mit Internetberechtigungen eine flüchtige dynamische Assembly generieren und deren Code ausführen kann:  
  
- Die dynamische Assembly verwendet nur öffentliche Typen und Member aus anderen Assemblys.  
  
- Die für diese Typen und Member erforderlichen Berechtigungen sind im Berechtigungssatz der teilweise vertrauenswürdigen Assembly enthalten.  
  
- Die Assembly wird nicht auf den Datenträger gespeichert.  
  
- Es werden keine Debugsymbole generiert. (`Internet`- und `LocalIntranet`-Berechtigungssätze enthalten nicht die notwendigen Berechtigungen.)  
  
<a name="Anonymously_Hosted_Dynamic_Methods"></a>
## <a name="anonymously-hosted-dynamic-methods"></a>Anonym gehostete dynamische Methoden  
 Anonym gehostete dynamische Methoden werden mithilfe der zwei <xref:System.Reflection.Emit.DynamicMethod>-Konstruktoren erstellt, die kein zugeordnetes Modul und keinen zugeordneten Typ angeben, <xref:System.Reflection.Emit.DynamicMethod.%23ctor%28System.String%2CSystem.Type%2CSystem.Type%5B%5D%29> und <xref:System.Reflection.Emit.DynamicMethod.%23ctor%28System.String%2CSystem.Type%2CSystem.Type%5B%5D%2CSystem.Boolean%29>. Diese Konstruktoren fügen die dynamischen Methoden in eine vom System bereitgestellte, vollständig vertrauenswürdige, sicherheitstransparente Assembly ein. Es sind keine Berechtigungen erforderlich, um diese Konstruktoren zu verwenden oder Code für die dynamischen Methoden auszugeben.  
  
 Stattdessen wird, wenn eine anonym gehostete dynamische Methode erstellt wird, wird die Aufrufliste erfasst. Wenn die Methode erstellt wird, werden anhand der erfassten Aufrufliste Sicherheitsanforderungen aufgestellt.  
  
> [!NOTE]
> Konzeptionell werden Anforderungen während der Erstellung der Methode gestellt. Das heißt, dass bei jeder Ausgabe einer MSIL-Anweisung Anforderungen gestellt werden könnten. In der aktuellen Implementierung werden alle Forderungen gestellt, wenn die <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A?displayProperty=nameWithType>-Methode aufgerufen wird oder wenn der JIT-Compiler (Just-in-Time) aufgerufen wird, falls die Methode ohne Aufruf von <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> aufgerufen wird.  
  
 Wenn die Anwendungsdomäne dies zulässt, können anonym gehostete dynamische Methoden JIT-Sichtbarkeitsprüfungen gemäß der folgenden Einschränkung überspringen: Die nicht öffentliche Typen und Member, auf die von einer anonym gehosteten dynamischen Methode zugegriffen wird, muss sich in Assemblys befinden, deren Berechtigungssätze mit dem Berechtigungssatz der ausgebenden Aufrufliste übereinstimmen oder eine Teilmenge davon darstellen. Diese eingeschränkte Fähigkeit zum Überspringen von JIT-Sichtbarkeitsprüfungen wird aktiviert, wenn die Anwendungsdomäne mit dem <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>-Flag <xref:System.Security.Permissions.ReflectionPermission> erteilt.  
  
- Wenn Ihre Methode nur öffentliche Typen und Member verwendet, sind während der Erstellung keine Berechtigungen erforderlich.  
  
- Wenn Sie angeben, dass JIT-Sichtbarkeitsprüfungen übersprungen werden sollen, enthält die Anforderung, die gestellt wird, wenn die Methode erstellt wird, <xref:System.Security.Permissions.ReflectionPermission> mit dem <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>-Flag und dem Berechtigungssatz der Assembly, die den nicht öffentlichen Member enthält, auf den zugegriffen wird.  
  
 Da der Berechtigungssatz des nicht öffentlichen Members berücksichtigt wird, kann teilweise vertrauenswürdiger Code, dem <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> gewährt wurde, seine Rechte nicht durch die Ausführung nicht öffentlicher Member vertrauenswürdiger Assemblys erhöhen.  
  
 Wie bei jedem anderen ausgegebenen Code auch, erfordert die Ausführung der dynamischen Methode alle Berechtigungen, die von den Methoden angefordert werden, die die dynamische Methode verwendet.  
  
 Die Systemassembly, die anonym gehostete dynamische Methoden hostet, verwendet das Transparenzmodell <xref:System.Security.SecurityRuleSet.Level1?displayProperty=nameWithType>. Hierbei handelt es sich um das Transparenzmodell, das in .NET Framework vor .NET Framework 4 verwendet wurde.  
  
 Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Reflection.Emit.DynamicMethod>-Klasse.  
  
### <a name="generating-anonymously-hosted-dynamic-methods-from-partially-trusted-code"></a>Generieren von anonym gehosteten dynamischen Methoden aus teilweise vertrauenswürdigem Code  
 Beachten Sie die Bedingungen, unter denen eine Assembly mit Internetberechtigungen eine anonym gehostete dynamische Methode generieren und ausführen kann:  
  
- Die dynamische Methode verwendet nur öffentliche Typen und Member. Wenn ihr Berechtigungssatz <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> enthält, kann sie nicht öffentliche Typen und Member jeder Assembly verwenden, deren Berechtigungssatz mit dem Berechtigungssatz der ausgebenden Assembly übereinstimmt oder eine Teilmenge davon darstellt.  
  
- Die für alle von der dynamischen Methode verwendeten Typen und Member erforderlichen Berechtigungen sind in dem Berechtigungssatz der teilweise vertrauenswürdigen Assembly enthalten.  
  
> [!NOTE]
> Dynamische Methoden unterstützen keine Debugsymbole.  
  
<a name="Dynamic_Methods_Associated_with_Existing_Assemblies"></a>
## <a name="dynamic-methods-associated-with-existing-assemblies"></a>Vorhandenen Assemblys zugeordnete dynamische Methoden  
 Um eine dynamische Methode einem Typ oder Modul in einer vorhandenen Assembly zuzuordnen, verwenden Sie einen der <xref:System.Reflection.Emit.DynamicMethod>-Konstruktoren, die den zugeordneten Typ bzw. das zugeordnete Modul angeben. Die Berechtigungen, die erforderlich sind, um diese Konstruktoren aufzurufen, variieren, da das Zuordnen einer dynamischen Methode zu einem vorhandenen Typ oder Modul der dynamischen Methode den Zugriff auf nicht öffentliche Typen und Member gewährt:  
  
- Eine dynamische Methode, die einem Typ zugeordnet ist, hat Zugriff auf alle Member dieses Typs, einschließlich privater Member, sowie auf alle internen Typen und Member in der Assembly, die den zugeordneten Typ enthält.  
  
- Eine dynamische Methode, die einem Modul zugeordnet ist, hat Zugriff auf alle `internal`-Typen und -Member (`Friend` in Visual Basic, `assembly` in Common Language Runtime-Metadaten) in dem Modul.  
  
 Darüber hinaus können Sie einen Konstruktor verwenden, der die Fähigkeit zum Überspringen der Sichtbarkeitsprüfungen des JIT-Compilers angibt. Auf diese Weise erhält Ihre dynamische Methode Zugriff auf alle Typen und Member in allen Assemblys, unabhängig von der Zugriffsebene.  
  
 Die vom Konstruktor angeforderten Berechtigungen sind davon abhängig, in welchem Umfang Sie Ihrer dynamischen Methode Zugriff erteilen möchten:  
  
- Wenn Ihre Methode nur öffentliche Typen und Member verwendet, und Sie sie Ihrem eigenen Typ bzw. Modul zuordnen, sind keine Berechtigungen erforderlich.  
  
- Wenn Sie angeben, dass JIT-Sichtbarkeitsprüfungen übersprungen werden sollen, erfordert der Konstruktor <xref:System.Security.Permissions.ReflectionPermission> mit dem <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType>-Flag.  
  
- Wenn Sie die dynamische Methode einem anderen Typ zuordnen, auch wenn es ein anderer Typ in Ihrer eigenen Assembly sein sollte, erfordert der Konstruktor <xref:System.Security.Permissions.ReflectionPermission> mit dem <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType>-Flag sowie <xref:System.Security.Permissions.SecurityPermission> mit dem <xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence?displayProperty=nameWithType>-Flag.  
  
- Wenn Sie die dynamische Methode einem Typ oder Modul in einer anderen Assembly zuordnen, erfordert der Konstruktor zwei Dinge: <xref:System.Security.Permissions.ReflectionPermission> mit dem <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>-Flag sowie den Berechtigungssatz der Assembly, die das andere Modul enthält. Das heißt, Ihre Aufrufliste muss alle Berechtigungen aus dem Berechtigungssatz des Zielmoduls enthalten, zuzüglich <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>.  
  
    > [!NOTE]
    > Um Abwärtskompatibilität zu gewährleisten, wenn die Anforderung des Zielberechtigungssatzes zuzüglich <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> fehlschlägt, erfordert der Konstruktor <xref:System.Security.Permissions.SecurityPermission> mit dem <xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence?displayProperty=nameWithType>-Flag.  
  
 Obgleich die Elemente in dieser Liste unter dem Aspekt des Berechtigungssatzes der ausgebenden Assembly beschrieben werden, sollten Sie daran denken, dass die Anforderungen an die gesamte Aufrufliste, einschließlich der Grenze der Anwendungsdomäne, gestellt werden.  
  
 Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Reflection.Emit.DynamicMethod>-Klasse.  
  
### <a name="generating-dynamic-methods-from-partially-trusted-code"></a>Generieren von dynamischen Methoden aus teilweise vertrauenswürdigem Code  
  
> [!NOTE]
> Die empfohlene Vorgehensweise zum Generieren dynamischer Methoden aus teilweise vertrauenswürdigem Code besteht in der Verwendung [anonym gehosteter dynamischer Methoden](#Anonymously_Hosted_Dynamic_Methods).  
  
 Beachten Sie die Bedingungen, unter denen eine Assembly mit Internetberechtigungen eine dynamische Methode generieren und ausführen kann:  
  
- Entweder ist die dynamische Methode dem Modul oder Typ zugeordnet, das/den sie ausgibt, oder ihr Berechtigungssatz enthält <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> und dieser ist einem Modul in einer Assembly zugeordnet, deren Berechtigungssatz mit dem Berechtigungssatz der ausgebenden Assembly übereinstimmt oder eine Teilmenge davon darstellt.  
  
- Die dynamische Methode verwendet nur öffentliche Typen und Member. Wenn ihr Berechtigungssatz <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> enthält und dieser einem Modul in einer Assembly zugeordnet ist, deren Berechtigungssatz mit dem Berechtigungssatz der ausgebenden Assembly übereinstimmt oder eine Teilmenge davon darstellt, kann sie Typen und Member verwenden, die in dem zugeordneten Modul als `internal` (`Friend` in Visual Basic, `assembly` in Common Language Runtime-Metadaten) markiert sind.  
  
- Die für alle von der dynamischen Methode verwendeten Typen und Member angeforderten Berechtigungen sind in dem Berechtigungssatz der teilweise vertrauenswürdigen Assembly enthalten.  
  
- Die dynamische Methode überspringt keine JIT-Sichtbarkeitsprüfungen.  
  
> [!NOTE]
> Dynamische Methoden unterstützen keine Debugsymbole.  
  
<a name="Version_Information"></a>
## <a name="version-information"></a>Versionsinformationen  
 Ab .NET Framework 4 wurde die computerweite Sicherheitsrichtlinie beseitigt, und Sicherheitstransparenz wird zum standardmäßigen Erzwingungsmechanismus. Weitere Informationen finden Sie unter [Sicherheitsänderungen](../security/security-changes.md).  
  
 Ab .NET Framework 2.0 Service Pack 1 ist <xref:System.Security.Permissions.ReflectionPermission> mit dem <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit?displayProperty=nameWithType>-Flag beim Ausgeben von dynamischen Assemblys und dynamischen Methoden nicht mehr erforderlich. In allen früheren Versionen von .NET Framework ist dieses Flag erforderlich.  
  
> [!NOTE]
> <xref:System.Security.Permissions.ReflectionPermission> mit dem <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit?displayProperty=nameWithType>-Flag ist standardmäßig in den benannten Berechtigungsätzen `FullTrust` und `LocalIntranet` enthalten, aber nicht im `Internet`-Berechtigungssatz. Aus diesem Grund kann in früheren Versionen von .NET Framework eine Bibliothek mit Internetberechtigungen nur dann verwendet werden, wenn dafür ein <xref:System.Security.PermissionSet.Assert%2A>-Element für <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit> ausgeführt wird. Diese Bibliotheken erfordern einen sorgfältigen Sicherheitsreview, da Codierungsfehler zu Sicherheitslücken führen können. In .NET Framework 2.SP1 0 ist es möglich, Code in teilweise vertrauenswürdigen Szenarios ohne Sicherheitsanforderungen auszugeben, da das Generieren von Code an sich keinen privilegierten Vorgang darstellt. Das bedeutet, dass der generierte Code nicht mehr Berechtigungen aufweist als die Assembly, die ihn ausgibt. Dies ermöglicht es, dass Bibliotheken, die Code ausgeben, sicherheitstransparent sein können, und beseitigt die Notwendigkeit der Assertion von <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit>, was das Schreiben einer sicheren Bibliothek vereinfacht.  
  
 Darüber hinaus wurde in .NET Framework 2.0 SP1 das <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>-Flag für den Zugriff auf nicht öffentliche Typen und Member aus teilweise vertrauenswürdigen dynamischen Methoden eingeführt. Frühere Versionen von .NET Framework erfordern das <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType>-Flag für dynamische Methoden, die auf nicht öffentliche Typen und Member zugreifen. Diese Berechtigung sollte niemals teilweise vertrauenswürdigem Code erteilt werden.  
  
 Schließlich wurden in .NET Framework 2.0 SP1 anonym gehostete Methoden eingeführt.  
  
### <a name="obtaining-information-on-types-and-members"></a>Abrufen von Informationen zu Typen und Member  
 Ab .NET Framework 2.0 sind keine Berechtigungen erforderlich, um Informationen über nicht öffentliche Typen und Member abzurufen. Reflektion wird verwendet, um Informationen abzurufen, die zum Ausgeben dynamischer Methoden erforderlich sind. Beispielsweise werden <xref:System.Reflection.MethodInfo>-Objekte verwendet, um Methodenaufrufe auszugeben. Frühere Versionen von .NET Framework erfordern <xref:System.Security.Permissions.ReflectionPermission> mit dem <xref:System.Security.Permissions.ReflectionPermissionFlag.TypeInformation?displayProperty=nameWithType>-Flag. Weitere Informationen finden Sie unter [Sicherheitsüberlegungen für die Reflektion](security-considerations-for-reflection.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Sicherheitsüberlegungen für die Reflektion](security-considerations-for-reflection.md)
- [Ausgeben von dynamischen Methoden und Assemblys](emitting-dynamic-methods-and-assemblies.md)
