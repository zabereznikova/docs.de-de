---
title: Sicherheitsüberlegungen für die Reflektion
description: Hier erfahren Sie mehr über die Sicherheitsaspekte für die Reflexion in .NET. Das Aufrufen von Informationen über Typen und Member ist zulässig, aber der Zugriff auf Member verfügt über Einschränkungen.
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], reflection
- MethodInfo parameters
- reflection, security
- partial trust,reflection
- nonpublic members
- reflection,partial trust
- link demands
ms.assetid: 42d9dc2a-8fcc-4ff3-b002-4ff260ef3dc5
ms.openlocfilehash: 0465cbd5ceb7d4f44bb6d10865fcbd17b8ed7af6
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865254"
---
# <a name="security-considerations-for-reflection"></a>Sicherheitsüberlegungen für die Reflektion

Die Reflektion bietet die Möglichkeit, Typ- und Memberinformationen abzurufen und auf Member zuzugreifen (d. h. Aufrufen von Methoden und Konstruktoren, Abrufen und Festlegen von Eigenschaftswerten, Hinzufügen und Entfernen von Ereignishandlern usw.). Die Verwendung von Reflektion, um Typ- und Memberinformationen abzurufen, ist nicht eingeschränkt. Jeglicher Code kann Reflektion verwenden, um die folgenden Aufgaben auszuführen:

- Auflisten von Typen und Membern und Prüfen von deren Metadaten.

- Auflisten und Prüfen von Assemblys und Modulen.

Das Verwenden von Reflektion, um auf Member zuzugreifen, ist dagegen Einschränkungen unterworfen. Ab .NET Framework 4 kann nur vertrauenswürdiger Code Reflektion für den Zugriff auf sicherheitskritische Member verwenden. Darüber hinaus kann nur vertrauenswürdiger Code Reflektion verwenden, um auf nicht öffentliche Member zuzugreifen, die in kompiliertem Code nicht direkt zugänglich sind. Schließlich muss Code, der über Reflektion auf einen sicherheitskritischen Member zugreift, jegliche Berechtigungen haben, die der sicherheitskritische Member erfordert, genauso wie bei kompiliertem Code.

Sofern die notwendigen Berechtigungen vorliegen, kann Code mithilfe von Reflektion die folgenden Zugriffsarten ausführen:

- Zugreifen auf öffentliche Member, die nicht sicherheitskritisch sind.

- Zugreifen auf nicht öffentliche Member, auf die kompilierter Code zugreifen könnte, wenn diese Member nicht sicherheitskritisch sind. Beispiele für solche nicht öffentlichen Member:

  - Geschützte Member der Basisklassen des aufrufenden Codes. (In Reflektion wird dies als Zugriff auf Familienebene bezeichnet.)

  - `internal`-Member (`Friend`-Member in Visual Basic) in der Assembly des aufrufenden Codes. (In Reflektion wird dies als Zugriff auf Assemblyebene bezeichnet.)

  - Private Member von anderen Instanzen der Klasse, die den aufrufenden Code enthält.

Zum Beispiel ist Code, der in einer Sandkastenanwendungsdomäne ausgeführt wird, auf den in dieser Liste beschriebenen Zugriff beschränkt, es sei denn, die Anwendungsdomäne gewährt zusätzliche Berechtigungen.

Ab .NET Framework 2.0 Service Pack 1 wird bei einem Zugriffsversuch auf Member, auf die normalerweise nicht zugegriffen werden kann, eine Anforderung nach dem Berechtigungssatz des Zielobjekts plus <xref:System.Security.Permissions.ReflectionPermission> mit dem <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType>-Flag erstellt. Code, der mit voller Vertrauenswürdigkeit ausgeführt wird (z.B. Code in einer Anwendung, die über die Befehlszeile gestartet wird), kann diese Berechtigungen immer erfüllen. (Dies unterliegt Einschränkungen beim Zugriff auf sicherheitskritische Member, wie dies in diesem Artikel weiter unten beschrieben ist.)

Optional kann eine Sandkastenanwendungsdomäne <xref:System.Security.Permissions.ReflectionPermission> mit dem <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType>-Flag gewähren, wie dies weiter unten in diesem Artikel im Abschnitt [Zugreifen auf Member, auf die normalerweise nicht zugegriffen werden kann](#accessingNormallyInaccessible) beschrieben ist.

<a name="accessingSecurityCritical"></a>

## <a name="accessing-security-critical-members"></a>Zugreifen auf sicherheitskritische Member

Ein Member ist sicherheitskritisch, wenn er das <xref:System.Security.SecurityCriticalAttribute>, wenn er zu einem Typ gehört, der das <xref:System.Security.SecurityCriticalAttribute> hat, oder wenn er sich in einer sicherheitskritischen Assembly befindet. Ab .NET Framework 4 gelten folgende Regeln für den Zugriff auf sicherheitskritische Member:

- Transparenter Code kann nicht über Reflektion auf sicherheitskritische Member zugreifen, selbst wenn der Code vollständig vertrauenswürdig ist. Es wird eine <xref:System.MethodAccessException>, <xref:System.FieldAccessException> oder <xref:System.TypeAccessException> ausgelöst.

- Code, der mit teilweiser Vertrauenswürdigkeit ausgeführt wird, wird als transparent behandelt.

Diese Regeln gelten immer, ganz gleich, ob auf einen sicherheitskritischen Member direkt aus kompiliertem Code oder über Reflektion zugegriffen wird.

Anwendungscode, der über die Befehlszeile ausgeführt wird, wird mit voller Vertrauenswürdigkeit ausgeführt. Solange Code nicht als transparent gekennzeichnet ist, kann er über Reflektion auf sicherheitskritische Member zugreifen. Wenn der gleiche Code mit teilweiser Vertrauenswürdigkeit ausgeführt wird (z. B. in einer Sandkastenanwendungsdomäne), bestimmt die Vertrauensebene der Assembly, ob der Zugriff auf sicherheitskritischen Code gewährt wird: Wenn die Assembly über einen starken Namen verfügt und im globalen Assemblycache installiert ist, ist sie eine vertrauenswürdige Assembly und sie kann sicherheitskritische Member aufrufen. Ist die Assembly nicht vertrauenswürdig ist, wird sie transparent, obwohl sie nicht als transparent gekennzeichnet wurde, und sie kann nicht auf sicherheitskritische Member zugreifen.

Weitere Informationen zum Sicherheitsmodell in .NET Framework 4 finden Sie unter [Änderungen der Sicherheit in .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).

## <a name="reflection-and-transparency"></a>Reflektion und Transparenz

Ab .NET Framework 4 bestimmt die Common Language Runtime (CLR) die Transparenzebene eines Typs oder Members auf der Grundlage mehrerer Faktoren (einschließlich der Vertrauensebene der Assembly und der Vertrauensebene der Anwendungsdomäne). Reflektion stellt die Eigenschaften <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Type.IsSecuritySafeCritical%2A> und <xref:System.Type.IsSecurityTransparent%2A> bereit, damit Sie die Transparenzebene eines Typs ermitteln können. Die folgende Tabelle enthält die gültigen Kombinationen dieser Eigenschaften.

|Sicherheitsstufe|IsSecurityCritical|IsSecuritySafeCritical|IsSecurityTransparent|
|--------------------|------------------------|----------------------------|---------------------------|
|Kritisch|`true`|`false`|`false`|
|Sicherheitskritisch|`true`|`true`|`false`|
|Transparent|`false`|`false`|`true`|

Ein Verwenden dieser Eigenschaften ist deutlich einfacher als das Untersuchen der Sicherheitsanmerkungen einer Assembly und der zugehörigen Typen, das Überprüfen der aktuellen Vertrauensebene und das Versuchen, die Laufzeitregeln zu duplizieren. Derselbe Typ kann z. B. sicherheitskritisch sein, wenn er über die Befehlszeile ausgeführt wird, oder sicherheitstransparent, wenn er in einer Sandkastenanwendungsdomäne ausgeführt wird.

Die Klassen <xref:System.Reflection.MethodBase>, <xref:System.Reflection.FieldInfo>, <xref:System.Reflection.Emit.TypeBuilder>, <xref:System.Reflection.Emit.MethodBuilder> und <xref:System.Reflection.Emit.DynamicMethod> haben ähnliche Eigenschaften. (Bei anderen Reflektionen und Abstraktionen für die Reflektionsausgabe werden Sicherheitsattribute auf die zugeordneten Methoden angewendet; bei Eigenschaften werden sie z. B. auf die Eigenschaftenaccessoren angewendet.)

<a name="accessingNormallyInaccessible"></a>

## <a name="accessing-members-that-are-normally-inaccessible"></a>Zugreifen auf Member, auf die normalerweise nicht zugegriffen werden kann

Um über Reflektion Methoden aufzurufen, auf die nach den Zugriffsregeln der Common Language Runtime nicht zugegriffen kann, muss Ihrem Code eine von zwei Berechtigungen gewährt werden:

- Damit Code einen beliebigen nicht öffentlichen Member aufrufen kann, muss dem Code <xref:System.Security.Permissions.ReflectionPermission> mit dem <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType>-Flag gewährt werden.

  > [!NOTE]
  > Standardmäßig verweigert die Sicherheitsrichtlinie diese Berechtigung für Code, der aus dem Internet stammt. Diese Berechtigung sollte niemals für Code gewährt werden, der aus dem Internet stammt.

- Damit Code beliebige nicht öffentliche Member aufrufen kann, sofern der Berechtigungssatz der Assembly, die den aufgerufenen Member enthält, mit dem Berechtigungssatz des aufrufenden Codes identisch oder eine Teilmenge dieses Berechtigungssatzes ist: Dem Code muss <xref:System.Security.Permissions.ReflectionPermission> mit dem <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>-Flag gewährt werden.

Beispiel: Angenommen, Sie gewähren einer Anwendungsdomäne Internetberechtigungen plus <xref:System.Security.Permissions.ReflectionPermission> mit dem <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>-Flag und führen anschließend eine Internetanwendung mit den beiden Assemblys A und B aus.

- Assembly A kann Reflektion verwenden, um auf private Member von Assembly B zuzugreifen, da der Berechtigungssatz der Assembly B keine Berechtigungen enthält, die A nicht gewährt wurden.

- Assembly A kann Reflektion nicht verwenden, um auf private Member von .NET Framework-Assemblys wie „mscorlib.dll“ zuzugreifen, denn „mscorlib.dll“ ist voll vertrauenswürdig und hat daher Berechtigungen, die Assembly A nicht gewährt wurden. Eine <xref:System.MemberAccessException> wird ausgelöst, wenn die Codezugriffssicherheit die Stapel zur Laufzeit durchläuft.

## <a name="serialization"></a>Serialisierung

Für Serialisierung bietet <xref:System.Security.Permissions.SecurityPermission> mit dem <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter%2A?displayProperty=nameWithType>-Flag die Möglichkeit, Member von serialisierbaren Typen unabhängig davon, ob grundsätzlich auf sie zugegriffen werden kann, abzurufen und festzulegen. Mit dieser Berechtigung kann Code den privaten Status einer Instanz erkennen und ändern. (Zusätzlich dazu, dass dem Typ die entsprechenden Berechtigungen gewährt werden, muss er in den Metadaten als serialisierbar [markiert](../../standard/attributes/applying-attributes.md) sein.)

## <a name="parameters-of-type-methodinfo"></a>Parameter des MethodInfo-Typs

Sie sollten keine öffentlichen Member schreiben, an die <xref:System.Reflection.MethodInfo>-Parameter übergeben werden. Dies gilt insbesondere für vertrauenswürdigen Code. Solche Member sind möglicherweise anfälliger für Schadsoftware. Nehmen Sie z. B. an, es gibt einen öffentlichen Member in hoch vertrauenswürdigem Code, und diesem Member wird ein <xref:System.Reflection.MethodInfo>-Parameter übergeben. Nehmen Sie weiter an, der öffentliche Member ruft indirekt die <xref:System.Reflection.MethodBase.Invoke%2A>-Methode für den bereitgestellten Parameter auf. Wenn der öffentliche Member nicht die erforderlichen Berechtigungsprüfungen ausführt, ist ein Aufruf <xref:System.Reflection.MethodBase.Invoke%2A>-Methode in jedem erfolgreich, weil das Sicherheitssystem feststellt, dass der Aufrufer hoch vertrauenswürdig ist. Selbst wenn Schadsoftware nicht die Berechtigung hat, die Methode direkt aufzurufen, kann sie dies weiterhin indirekt durch Aufrufen des öffentlichen Members tun.

## <a name="version-information"></a>Versionsinformationen

- Ab .NET Framework 4 kann transparenter Code Reflektion nicht für den Zugriff auf sicherheitskritische Member verwenden.

- Das <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>-Flag wurde in .NET Framework 2.0 Service Pack 1 eingeführt. Frühere Versionen von .NET Framework erfordern das <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType>-Flag für Code, in dem Reflektion verwendet wird, um auf nicht öffentliche Member zuzugreifen. Diese Berechtigung sollte in keinem Fall teilweise vertrauenswürdigem Code erteilt werden.

- Ab .NET Framework 2.0 sind keine Berechtigungen erforderlich, um über Reflektion Informationen über nicht öffentliche Typen und Member abzurufen. In früheren Versionen ist <xref:System.Security.Permissions.ReflectionPermission> mit dem <xref:System.Security.Permissions.ReflectionPermissionFlag.TypeInformation?displayProperty=nameWithType>-Flag erforderlich.

## <a name="see-also"></a>Siehe auch

- <xref:System.Security.Permissions.ReflectionPermissionFlag>
- <xref:System.Security.Permissions.ReflectionPermission>
- <xref:System.Security.Permissions.SecurityPermission>
- [Sicherheitsänderungen](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes)
- [Codezugriffssicherheit](../misc/code-access-security.md)
- [Sicherheitsaspekte bei der Reflektionsausgabe](security-issues-in-reflection-emit.md)
- [Anzeigen von Typinformationen](viewing-type-information.md)
- [Anwenden von Attributen](../../standard/attributes/applying-attributes.md)
- [Zugreifen auf benutzerdefinierte Attribute](accessing-custom-attributes.md)
