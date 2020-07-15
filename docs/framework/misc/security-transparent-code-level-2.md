---
title: Sicherheitstransparenter Code, Ebene 2
description: Verstehen Sie den transparenten Code der Ebene 2. Weitere Informationen finden Sie unter Verwendungs Beispiele und Verhalten, außer Kraft setzen von Mustern, Vererbungs Regeln und mehr.
ms.date: 03/30/2017
helpviewer_keywords:
- transparency
- level 2 transparency
- security-transparent code
- security-critical code
ms.assetid: 4d05610a-0da6-4f08-acea-d54c9d6143c0
ms.openlocfilehash: 3b87a48ac3f9925fd868be9e58d5904014ca6c09
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309208"
---
# <a name="security-transparent-code-level-2"></a>Sicherheitstransparenter Code, Ebene 2

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

Transparenz der Ebene 2 wurde in der .NET Framework 4 eingeführt. Die drei Grundsätze dieses Modells sind transparenter Code, sicherheitsgeschützter Code und sicherheitskritischer Code.

- Transparenter Code, einschließlich Code, der mit voller Vertrauenswürdigkeit ausgeführt wird, kann anderen transparenten Code oder sicherheitsgeschützten Code nur aufrufen. Er kann nur Aktionen durchführen, die von der domänenspezifischen Berechtigungseinstellung für teilweise Vertrauenswürdigkeit zugelassen werden. Transparenter Code ist nicht für die folgenden Vorgänge vorgesehen:

  - Ausführen eines <xref:System.Security.CodeAccessPermission.Assert%2A>-Vorgangs oder einer Berechtigungserweiterung.

  - Der Code darf keinen unsicheren oder nicht überprüfbaren Code enthalten.

  - Direktes Aufrufen von wichtigem Code.

  - Aufrufen von systemeigenen Code oder von Code mit dem <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>-Attribut.

  - Aufrufen eines Members, der von einem <xref:System.Security.Permissions.SecurityAction.LinkDemand>-Feld geschützt wird.

  - Erben von wichtigen Typen.

  Außerdem können transparente Methoden keine wichtigen virtuellen Methoden überschreiben oder wichtige Schnittstellenmethoden implementieren.

- Sicherheitsgeschützter Code ist vollständig vertrauenswürdig, kann aber durch transparenten Code aufgerufen werden. Er macht einen beschränkten Oberflächenbereich mit vollständig vertrauenswürdigem Code verfügbar. Korrektheits- und Sicherheitsüberprüfungen werden in sicherheitsgeschütztem Code ausgeführt.

- Mit sicherheitskritischem Code kann jeder Code aufgerufen werden, und er ist vollständig vertrauenswürdig, kann jedoch nicht von transparentem Code aufgerufen werden.

## <a name="usage-examples-and-behaviors"></a>Verwendungsbeispiele und Verhalten

Verwenden Sie zum Angeben von .NET Framework 4-Regeln (Transparenz der Ebene 2) die folgende Anmerkung für eine Assembly:

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level2)]
```

Um die .NET Framework 2.0-Regeln (Transparenz der Ebene 1) festzulegen, verwenden Sie die folgende Anmerkung:

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level1)]
```

Wenn Sie keine Assembly mit Anmerkungen versehen, werden standardmäßig die .NET Framework 4-Regeln verwendet. Es wird jedoch empfohlen, das- <xref:System.Security.SecurityRulesAttribute> Attribut anstelle der Standardeinstellung zu verwenden.

### <a name="assembly-wide-annotation"></a>Assemblyweite Anmerkung

Die folgenden Regeln gelten für die Verwendung von Attributen auf Assemblyebene:

- Keine Attribute: Wenn Sie keine Attribute angeben, interpretiert die Laufzeit den gesamten Code als sicherheitskritisch, es sei denn, die Einstufung als sicherheitskritisch verletzt eine Vererbungsregel (z. B. beim Überschreiben oder Implementieren einer transparenten virtuellen oder Schnittstellenmethode). In diesen Fällen sind die Methoden sicherheitsgeschützt. Wenn kein Attribut angegeben wird, bestimmt die Common Language Runtime die Transparenzregeln.

- `SecurityTransparent`: Der gesamte Code ist transparent, und die gesamte Assembly führt keine privilegierten oder unsicheren Aktionen durch.

- `SecurityCritical`: Der gesamte Code, der von Typen in dieser Assembly eingeführt wird, ist wichtig, und der gesamte andere Code ist transparent. Dieses Szenario ähnelt dem Fall, dass keine Attribute angegeben werden, allerdings werden die Transparenzregeln nicht automatisch von der Common Language Runtime bestimmt. Wenn Sie beispielsweise eine virtuelle oder abstrakte Methode überschreiben oder eine Schnittstellenmethode implementieren, ist diese Methode standardmäßig transparent. Sie müssen die Methode explizit als `SecurityCritical` oder `SecuritySafeCritical` kommentieren, andernfalls wird zur Ladezeit eine <xref:System.TypeLoadException> ausgelöst. Diese Regel gilt auch, wenn die Basisklasse und die abgeleitete Klasse sich in der gleichen Assembly befinden.

- `AllowPartiallyTrustedCallers` (nur Ebene 2): Der gesamte Code ist standardmäßig transparent. Einzelne Typen und Member können jedoch andere Attribute haben.

In der folgenden Tabelle wird das Verhalten auf Assemblyebene für Ebene 2 mit Ebene 1 verglichen.

|Assembly-Attribut|Ebene 2|Ebene 1|
|------------------------|-------------|-------------|
|Kein Attribut in einer teilweise vertrauenswürdigen Assembly|Typen und Member sind standardmäßig transparent, aber können sicherheitskritisch oder sicherheitsgeschützt sein.|Alle Typen und Member sind transparent.|
|Kein Attribut|Wenn kein Attribut angegeben wird, bestimmt die Common Language Runtime die Transparenzregeln. Alle Typen und Member sind sicherheitskritisch, es sei denn, die Einstufung als sicherheitskritisch verletzt eine Vererbungsregel.|In einer voll vertrauenswürdigen Assembly (im globalen Assemblycache oder als voll vertrauenswürdig in der `AppDomain` identifiziert) sind alle Typen transparent, und alle Member sind sicherheitsgeschützt.|
|`SecurityTransparent`|Alle Typen und Member sind transparent.|Alle Typen und Member sind transparent.|
|`SecurityCritical(SecurityCriticalScope.Everything)`|Nicht zutreffend| Alle Typen und Member sind sicherheitskritisch.|
|`SecurityCritical`|Der gesamte Code, der von Typen in dieser Assembly eingeführt wird, ist wichtig, und der gesamte andere Code ist transparent. Wenn Sie eine virtuelle oder abstrakte Methode überschreiben oder eine Schnittstellenmethode implementieren, müssen Sie diese Methode explizit per Anmerkung als `SecurityCritical` oder `SecuritySafeCritical` kennzeichnen.|Der gesamte Code ist standardmäßig transparent. Einzelne Typen und Member können jedoch andere Attribute haben.|

### <a name="type-and-member-annotation"></a>Typ- und Memberanmerkung

Die Sicherheitsattribute, die auf einen Typ angewendet werden, gelten auch für die Elemente, die vom Typ eingeführt werden. Allerdings gelten sie nicht für virtuelle oder abstrakte Überschreibungen der Basisklassen- oder  Schnittstellenimplementierungen. Die folgenden Regeln gelten für die Verwendung von Attributen auf Typ- und Memberebene:

- `SecurityCritical`: Der Typ oder Member ist wichtig und kann nur von voll vertrauenswürdigem Code aufgerufen werden. Methoden, die in einem sicherheitsrelevanten Typ eingeführt werden, sind wichtig.

    > [!IMPORTANT]
    > Virtuelle und abstrakte Methoden, die in Basisklassen oder Schnittstellen eingeführt und überschrieben oder in einer sicherheitskritischen Klasse implementiert werden, sind standardmäßig transparent. Sie müssen als `SecuritySafeCritical` oder `SecurityCritical` identifiziert werden.

- `SecuritySafeCritical`: Der Typ oder Member ist sicherheitsgeschützt. Allerdings kann der Typ oder Member von transparentem (teilweise vertrauenswürdigem) Code aufgerufen werden und ist so leistungsfähig wie jeder andere wichtige Code. Der Code muss hinsichtlich der Sicherheit überwacht werden.

## <a name="override-patterns"></a>Überschreibungsmuster

In der folgenden Tabelle werden die für die Transparenz der Ebene 2 zulässigen Methodenüberschreibungen aufgeführt.

|Basis virtuell/Schnittstellenmember|Überschreiben/Schnittstelle|
|------------------------------------|-------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

## <a name="inheritance-rules"></a>Vererbungsregeln

In diesem Abschnitt wird `Transparent`, `Critical` und `SafeCritical` Code basierend auf Zugriff und Funktionalität folgende Reihenfolge zugewiesen:

`Transparent` < `SafeCritical` < `Critical`

- Regeln für Typen: Von links nach rechts wird der Zugriff immer stärker eingeschränkt. Abgeleitete Typen müssen mindestens so restriktiv wie der Basistyp sein.

- Regeln für Methoden: Der Zugriff abgeleiteter Methoden kann nicht vom Zugriff der Basismethode abweichen. Standardmäßig sind alle abgeleiteten Methoden, die nicht mit einer Anmerkung versehen sind, `Transparent`. Ableitungen wichtiger Typen bewirken, dass eine Ausnahme ausgelöst wird, wenn die überschriebene Methode nicht explizit als `SecurityCritical` gekennzeichnet ist.

In der folgenden Tabelle werden die zulässigen Muster der Typenvererbung aufgeführt.

|Basisklasse|Abgeleitete Klasse kann Folgendes sein:|
|----------------|--------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`Transparent`|`Critical`|
|`SafeCritical`|`SafeCritical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Critical`|

In der folgenden Tabelle werden die unzulässigen Muster der Typenvererbung aufgeführt.

|Basisklasse|Abgeleitete Klasse kann Folgendes nicht sein:|
|----------------|-----------------------------|
|`SafeCritical`|`Transparent`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

In der folgenden Tabelle werden die zulässigen Muster der Methodenvererbung aufgeführt.

|Basismethode|Abgeleitete Methode kann Folgendes sein:|
|-----------------|---------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

In der folgenden Tabelle werden die unzulässigen Muster der Methodenvererbung aufgeführt.

|Basismethode|Abgeleitete Methode kann Folgendes nicht sein:|
|-----------------|------------------------------|
|`Transparent`|`Critical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

> [!NOTE]
> Diese Vererbungsregeln gelten für Typen und Member der Ebene 2. Typen in Assemblys der Ebene 1 können von sicherheitskritischen Typen und Membern der Ebene 2 erben. Daher müssen Typen und Member der Ebene 2 separate  Vererbungsanforderungen für Erben der Ebene 1 aufweisen.

## <a name="additional-information-and-rules"></a>Zusätzliche Informationen und Regeln

### <a name="linkdemand-support"></a>LinkDemand-Unterstützung

Das Transparenzmodell der Ebene 2 ersetzt <xref:System.Security.Permissions.SecurityAction.LinkDemand> durch das <xref:System.Security.SecurityCriticalAttribute>-Attribut. In Legacycode (Stufe 1) wird ein <xref:System.Security.Permissions.SecurityAction.LinkDemand> automatisch als ein <xref:System.Security.Permissions.SecurityAction.Demand> behandelt.

### <a name="reflection"></a>Spiegelung

Das Aufrufen einer wichtigen Methode oder das Lesen eines wichtigen Felds löst eine Anforderung vollständiger Vertrauenswürdigkeit aus (wie beim Aufrufen einer privaten Methode oder eines privaten Felds). Aus diesem Grund kann voll vertrauenswürdiger Code eine wichtige Methode aufrufen, teilweise vertrauenswürdiger Code hingegen nicht.

Die folgenden Eigenschaften wurden dem Namespace "<xref:System.Reflection>" hinzugefügt, um zu bestimmen, ob der Typ, die Methode oder das Feld `SecurityCritical`, `SecuritySafeCritical` oder `SecurityTransparent` ist:  <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> und <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>. Verwenden Sie diese Eigenschaften zur Bestimmung der Transparenz durch Reflektion statt durch Prüfen auf das Vorhandensein des Attributs. Die Transparenzregeln sind komplex, und das Prüfen auf das Attribut ist möglicherweise nicht ausreichend.

> [!NOTE]
> Eine `SafeCritical` Methode gibt `true` sowohl für <xref:System.Type.IsSecurityCritical%2A> als auch zurück <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> , da `SafeCritical` tatsächlich kritisch ist (Sie hat die gleichen Funktionen wie kritischer Code, aber Sie kann aus transparentem Code aufgerufen werden).

Dynamische Methoden erben die Transparenz der Module, denen sie zugeordnet sind. Sie erben nicht die Transparenz des Typs (sofern sie einem Typ zugeordnet sind).

### <a name="skip-verification-in-full-trust"></a>Überspringen der Überprüfung bei vollständiger Vertrauenswürdigkeit

Sie können die Überprüfung für vollständig vertrauenswürdige transparente Assemblys überspringen, indem Sie die Eigenschaft "<xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A>" im Attribut "<xref:System.Security.SecurityRulesAttribute>" auf "`true`" festlegen:

`[assembly: SecurityRules(SecurityRuleSet.Level2, SkipVerificationInFullTrust = true)]`

Die Eigenschaft "<xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A>" ist standardmäßig "`false`" und muss daher auf "`true`" festgelegt werden, um die Überprüfung zu überspringen. Dies sollte nur zu Optimierungszwecken erfolgen. Stellen Sie sicher, dass der transparente Code in der Assembly überprüfbar ist. verwenden Sie dazu die `transparent` Option im [Tool "Peer Verify](../tools/peverify-exe-peverify-tool.md)".

## <a name="see-also"></a>Weitere Informationen

- [Sicherheits transparenter Code, Ebene 1](security-transparent-code-level-1.md)
- [Sicherheitsänderungen](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes)
