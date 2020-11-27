---
title: Sicherheitstransparenter Code, Ebene 1
description: Sehen Sie sich die Beispiele für Transparenz, Transparenz und Transparenz der Ebene 1 an.
ms.date: 03/30/2017
helpviewer_keywords:
- transparent
- SecurityTreatAsSafeAttribute
- SecurityTransparentAttribute
- SecurityCriticalAttribute
- security-transparent code
- security [.NET Framework], security-transparent code
ms.assetid: 5fd8f46d-3961-46a7-84af-2eb1f48e75cf
ms.openlocfilehash: 97acccdc1dcab11e42d116f4743e1182029e2dd6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288189"
---
# <a name="security-transparent-code-level-1"></a>Sicherheitstransparenter Code, Ebene 1

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 Transparenz ermöglicht Entwicklern, sicherere .NET Framework-Bibliotheken zu schreiben, die Funktionalität für teilweise vertrauenswürdigen Code verfügbar machen. Transparenz der Ebene 1 wurde in .NET Framework, Version 2.0, eingeführt und wurde hauptsächlich bei Microsoft verwendet. Ab .NET Framework 4 können Sie [Transparenz der Ebene 2](security-transparent-code-level-2.md)verwenden. Allerdings wurde Transparenz der Ebene 1 beibehalten, damit Legacycode identifiziert werden kann, der mit den früheren Sicherheitsregeln ausgeführt werden muss.  
  
> [!IMPORTANT]
> Geben Sie Transparenz der Ebene 1 nur aus Kompatibilitätsgründen an, d. h., geben Sie Ebene 1 nur für Code an, der mit .NET Framework 3.5 oder niedriger entwickelt wurde und für den <xref:System.Security.AllowPartiallyTrustedCallersAttribute> verwendet bzw. für den das Transparenzmodell nicht verwendet wird. Verwenden Sie Transparenz der Ebene 1 z. B. für .NET Framework 2.0-Assemblys, die Aufrufe von teilweise vertrauenswürdigen Aufrufern (APTCA) ermöglichen. Verwenden Sie für Code, der für die .NET Framework 4 entwickelt wurde, immer Transparenz der Ebene 2.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
- [Das Transparenzmodell der Ebene 1](#the_level_1_transparency_model)  
  
- [Transparenzattribute](#transparency_attributes)  
  
- [Beispiele für Sicherheitstransparenz](#security_transparency_examples)  
  
<a name="the_level_1_transparency_model"></a>

## <a name="the-level-1-transparency-model"></a>Das Transparenzmodell der Ebene 1  

 Wenn Sie Transparenz der Ebene 1 verwenden, nutzen Sie ein Sicherheitsmodell, das Code in sicherheitstransparente, sicherheitsgeschützte und sicherheitskritische Methoden unterteilt.  
  
 Sie können eine gesamte Assembly, einige Klassen in einer Assembly oder einige Methoden in einer Klasse als sicherheitstransparent kennzeichnen. Sicherheitstransparenter Code kann keine Berechtigungen heraufstufen. Diese Einschränkung hat drei Konsequenzen:  
  
- Sicherheitstransparenter Code kann keine <xref:System.Security.Permissions.SecurityAction.Assert>-Aktionen durchführen.  
  
- Jeder Linkaufruf, der von sicherheitstransparentem Code umgesetzt wird, wird zu einem vollständigen Aufruf.  
  
- Jeder unsichere (nicht überprüfbare) Code, der in sicherheitstransparentem Code ausgeführt werden muss, verursacht einen vollständigen Aufruf der Sicherheitsberechtigung <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>.  
  
 Diese Regeln werden während der Ausführung durch die Common Language Runtime (CLR) erzwungen. Sicherheitstransparenter Code übergibt alle Sicherheitsanforderungen des Codes zurück an seine Aufrufer. Anforderungen, die durch sicherheitstransparenten Code fließen, können keine Berechtigungen heraufstufen. Wenn eine wenig vertrauenswürdige Anwendung sicherheitstransparenten Code aufruft und eine Anforderung für eine höhere Berechtigung verursacht, fließt die Anforderung zurück zum wenig vertrauenswürdigem Code und kann nicht ausgeführt werden. Der sicherheitstransparente Code kann die Anforderung nicht aufhalten, da er keine Assert-Aktionen ausführen kann. Wenn derselbe sicherheitstransparente Code von voll vertrauenswürdigem Code aufgerufen wird, kann die Anforderung erfolgreich ausgeführt werden.  
  
 Sicherheitskritisch ist das Gegenteil von sicherheitstransparent. Sicherheitskritischer Code wird mit voller Vertrauenswürdigkeit ausgeführt und kann alle privilegierten Vorgänge ausführen. Sicherheitsgeschützter Code ist privilegierter Code, an dem eine umfassende Sicherheitsüberwachung durchgeführt wurde, um sicherzustellen, dass er teilweise vertrauenswürdigen Aufrufern nicht gestattet, Ressourcen zu verwenden, für die sie keine Zugriffsberechtigung haben.  
  
 Sie müssen Transparenz explizit anwenden. Der Großteil des Codes, der die Datenbearbeitung und Logik behandelt, kann in der Regel als sicherheitstransparent markiert werden, wohingegen die geringere Menge an Code, die Berechtigungen heraufstuft, als sicherheitskritisch oder sicherheitsgeschützt markiert wird.  
  
> [!IMPORTANT]
> Transparenz der Ebene 1 gilt nur für den Assemblybereich und wird nicht zwischen Assemblys erzwungen. Transparenz der Ebene 1 wurde hauptsächlich bei Microsoft für Sicherheitsüberwachungszwecke verwendet. Sicherheitstransparenter Code in einer Assembly kann auf sicherheitskritische Typen und Member in einer Assembly der Ebene 1 zugreifen. Es ist wichtig, dass Sie Linkaufrufe für volle Vertrauenswürdigkeit in allen sicherheitskritischen Typen und Membern der Ebene 1 ausführen. Sicherheitsgeschützte Typen und Member müssen auch bestätigen, dass Aufrufer über Berechtigungen für geschützte Ressourcen verfügen, auf die der Typ oder Member zugreift.  
  
 Für die Abwärtskompatibilität mit früheren Versionen von .NET Framework gelten alle Member, die nicht durch Transparenzattribute gekennzeichnet sind, als sicherheitsgeschützt. Alle Typen, die nicht mit einer Anmerkung versehen sind, werden als transparent betrachtet. Es gibt keine statischen Analyseregeln für die Überprüfung der Transparenz. Daher müssen Sie Transparenzfehler gegebenenfalls zur Laufzeit debuggen.  
  
<a name="transparency_attributes"></a>

## <a name="transparency-attributes"></a>Transparenzattribute  

 Die folgende Tabelle beschreibt die drei Attribute, die Sie verwenden, um den Code mit Anmerkungen für die Transparenz zu versehen.  
  
|Attribut|BESCHREIBUNG|  
|---------------|-----------------|  
|<xref:System.Security.SecurityTransparentAttribute>|Nur auf Assemblyebene zulässig. Identifiziert alle Typen und Member in der Assembly als sicherheitstransparent. Die Assembly kann keinen sicherheitskritischen Code enthalten.|  
|<xref:System.Security.SecurityCriticalAttribute>|Bei Verwendung auf Assemblyebene ohne die <xref:System.Security.SecurityCriticalAttribute.Scope%2A>-Eigenschaft wird der gesamte Code in der Assembly standardmäßig als sicherheitstransparent identifiziert, aber es wird angegeben, dass die Assembly sicherheitskritischen Code enthalten kann.<br /><br /> Bei Verwendung auf Klassenebene wird die Klasse oder Methode als sicherheitskritisch identifiziert, jedoch nicht die Member der Klasse. Um alle Member als sicherheitskritisch festzulegen, setzen Sie die <xref:System.Security.SecurityCriticalAttribute.Scope%2A>-Eigenschaft auf <xref:System.Security.SecurityCriticalScope.Everything>.<br /><br /> Bei Verwendung auf Memberebene wird das Attribut nur auf diesen Member angewendet.<br /><br /> Die als sicherheitskritisch identifizierten Klassen oder Member können Berechtigungen heraufstufen. **Wichtig:**  In Transparenz der Ebene 1 werden sicherheitskritische Typen und Member als Sicherheits geschützt behandelt, wenn Sie von außerhalb der Assembly aufgerufen werden. Sie sollten sicherheitskritische Typen und Member mit einem Linkaufruf schützen, um eine nicht autorisierte Heraufstufung der Berechtigungen zu schützen.|  
|<xref:System.Security.SecuritySafeCriticalAttribute>|Identifiziert sicherheitskritischen Code, auf den von sicherheitstransparentem Code in der Assembly zugegriffen werden kann. Andernfalls kann sicherheitstransparenter Code nicht auf private oder interne sicherheitskritische Member in derselben Assembly zugreifen. Wenn dies möglich wäre, würde sicherheitskritischer Code beeinflusst, und unerwartete Heraufstufungen von Berechtigungen wären möglich. Sicherheitsgeschützter Code sollte einer strengen Sicherheitsüberprüfung unterzogen werden. **Hinweis:**  Sicherheits geschützte Typen und Member müssen die Berechtigungen von Aufrufern validieren, um zu bestimmen, ob der Aufrufer über Berechtigungen für den Zugriff auf geschützte Ressourcen verfügt.|  
  
 Das <xref:System.Security.SecuritySafeCriticalAttribute>-Attribut ermöglicht sicherheitstransparentem Code den Zugriff auf sicherheitskritische Member in derselben Assembly. Der sicherheitstransparente und der sicherheitskritische Code in Ihrer Assembly ist gewissermaßen in zwei Assemblys unterteilt. Der sicherheitstransparente Code kann die privaten oder internen Member des sicherheitskritischen Codes nicht sehen. Darüber hinaus wird der sicherheitskritische Code im Allgemeinen hinsichtlich des Zugriffs auf seine öffentliche Schnittstelle überwacht. Auf einen privaten oder internen Status sollte außerhalb der Assembly nicht zugegriffen werden können. Diese Status sollten isoliert bleiben. Das <xref:System.Security.SecuritySafeCriticalAttribute>-Attribut hält die Isolation des Status zwischen sicherheitstransparentem und sicherheitskritischem Code aufrecht, aber bietet die Möglichkeit, die Isolation bei Bedarf zu überschreiben. Sicherheitstransparenter Code kann nicht auf privaten oder internen sicherheitskritischen Code zugreifen, es sei denn, die entsprechenden Member wurden mit <xref:System.Security.SecuritySafeCriticalAttribute> markiert. Vor dem Anwenden des <xref:System.Security.SecuritySafeCriticalAttribute> überwachen Sie den Member, als ob er öffentlich verfügbar wäre.  
  
### <a name="assembly-wide-annotation"></a>Assemblyweite Anmerkung  

 Die folgende Tabelle beschreibt die Auswirkungen der Verwendung von Sicherheitsattributen auf Assemblyebene.  
  
|Assembly-Attribut|Assemblyzustand|  
|------------------------|--------------------|  
|Kein Attribut in einer teilweise vertrauenswürdigen Assembly|Alle Typen und Member sind transparent.|  
|Kein Attribut in einer voll vertrauenswürdigen Assembly (im globalen Assemblycache oder als voll vertrauenswürdig in der `AppDomain` identifiziert)|Alle Typen sind transparent, und alle Member sind sicherheitskritisch und sicherheitsgeschützt.|  
|`SecurityTransparent`|Alle Typen und Member sind transparent.|  
|`SecurityCritical(SecurityCriticalScope.Everything)`| Alle Typen und Member sind sicherheitskritisch.|  
|`SecurityCritical`|Der gesamte Code ist standardmäßig transparent. Einzelne Typen und Member können jedoch andere Attribute haben.|  
  
<a name="security_transparency_examples"></a>

## <a name="security-transparency-examples"></a>Beispiele für Sicherheitstransparenz  

 Verwenden Sie die folgende Assemblyanmerkung für die Verwendung die .NET Framework 2.0-Transparenzregeln (Transparenz der Ebene 1):  
  
```csharp
[assembly: SecurityRules(SecurityRuleSet.Level1)]  
```  
  
 Wenn Sie eine gesamte Assembly als transparent kennzeichnen möchten, um anzugeben, dass die Assembly keinen kritischen Code enthält und keine Berechtigungen heraufstuft, können Sie der Assembly mit dem folgenden Attribut explizit Transparenz hinzufügen:  
  
```csharp  
[assembly: SecurityTransparent]  
```  
  
 Wenn Sie kritischen und sicherheitstransparenten Code in derselben Assembly verwenden möchten, markieren Sie die Assembly zunächst wie folgt mit dem <xref:System.Security.SecurityCriticalAttribute>-Attribut, um anzugeben, dass die Assembly kritischen Code enthalten kann:  
  
```csharp  
[assembly: SecurityCritical]  
```  
  
 Wenn Sie sicherheitskritische Aktionen durchführen möchten, müssen Sie den Code, der die kritische Aktion durchführen wird, explizit mit einem weiteren <xref:System.Security.SecurityCriticalAttribute>-Attribut kennzeichnen, wie im folgenden Codebeispiel dargestellt:  
  
```csharp  
[assembly: SecurityCritical]  
public class A  
{  
    [SecurityCritical]  
    private void Critical()  
    {  
        // critical  
    }  
  
    public int SomeProperty  
    {  
        get {/* transparent */ }  
        set {/* transparent */ }  
    }  
}  
public class B  
{
    internal string SomeOtherProperty  
    {  
        get { /* transparent */ }  
        set { /* transparent */ }  
    }  
}  
```  
  
 Der vorhergehende Code ist transparent, mit Ausnahme der `Critical`-Methode, die explizit als sicherheitskritisch markiert ist. Transparenz ist die Standardeinstellung, selbst mit dem auf Assemblyebene zugewiesenen <xref:System.Security.SecurityCriticalAttribute>-Attribut.  
  
## <a name="see-also"></a>Weitere Informationen

- [Sicherheitstransparenter Code, Ebene 2](security-transparent-code-level-2.md)
- [Sicherheitsänderungen](/previous-versions/dotnet/framework/security/security-changes)
