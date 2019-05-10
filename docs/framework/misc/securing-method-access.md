---
title: Sichern des Methodenzugriffs
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- code security, method access
- secure coding, method access
- security [.NET Framework], method access
- method access security
ms.assetid: f7c2d6ec-3b18-4e0e-9991-acd97189d818
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d9d423ef71b76b2dcbbf2812e13850922fb50ac0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625890"
---
# <a name="securing-method-access"></a>Sichern des Methodenzugriffs
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 Einige Methoden sind möglicherweise nicht geeignet, um den Aufruf von beliebigem, nicht vertrauenswürdigen Code zu gestatten. Solche Methoden weisen gewisse Risiken: Die Methode bietet möglicherweise eingeschränkte Informationen; es evtl. alle an sie übergebenen Informationen; Fehler beim Überprüfen der auf den Parametern kann es nicht; oder mit falschen Parametern möglicherweise Fehlfunktionen oder schädliche Aktionen ausgeführt werden. Sie sollten sich dieser Fälle bewusst sein und Maßnahmen zum Schutz der Methode ergreifen.  
  
 In einigen Fällen müssen Sie Methoden möglicherweise einschränken, die nicht für die öffentliche Verwendung vorgesehen sind, aber dennoch öffentlich sein müssen. Möglicherweise liegt z. B. eine Schnittstelle vor, die zwischen Ihren eigenen DLLs aufgerufen werden muss und daher öffentlich sein muss. Sie möchten sie aber nicht öffentlich verfügbar machen, damit sie weder von Kunden verwendet wird noch bösartigem Code die Gelegenheit bietet, den Einstiegspunkt in Ihre Komponente verfügbar zu machen. Eine anderer häufiger Grund zum Einschränken einer Methode, die nicht für die öffentliche Verwendung vorgesehen ist (jedoch öffentlich sein muss), ist es zu vermeiden, dass diese überaus interne Schnittstelle dokumentiert und unterstützt werden muss.  
  
 Verwalteter Code bietet mehrere Möglichkeiten zum Einschränken des Zugriffs auf Methoden:  
  
- Einschränken des Zugriffsbereichs auf die Klasse, Assembly oder abgeleiteten Klassen, wenn diese vertrauenswürdig sind. Dies ist die einfachste Möglichkeit, um den Methodenzugriff einzuschränken. Beachten Sie, dass abgeleitete Klassen im Allgemeinen weniger vertrauenswürdig sind als die Klasse, von der sie abgeleitet wurden, obwohl sie in einigen Fällen die Identität der übergeordneten Klasse teilen. Leiten Sie insbesondere keine Vertrauenswürdigkeit vom Schlüsselwort **geschützt**, wird die nicht unbedingt im Sicherheitskontext verwendet.  
  
- Beschränken Sie den Methodenzugriff auf Aufrufer mit einer angegebenen Identität – im Wesentlichen eine bestimmte [Beweise](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7y5x1hcd%28v=vs.100%29) (starker Name, Herausgeber, Zone usw.), die Sie auswählen.  
  
- Schränken Sie den Methodenzugriff auf Aufrufer mit von Ihnen ausgewählten Berechtigungen ein.  
  
 Die deklarative Sicherheit ermöglicht es Ihnen gleichermaßen, die Vererbung von Klassen zu kontrollieren. Sie können **InheritanceDemand** die folgenden Schritte ausführen:  
  
- Für abgeleitete Klassen eine bestimmte Identität oder Berechtigung anfordern.  
  
- Für abgeleitete Klassen, die bestimmte Methoden außer Kraft setzen, eine bestimmte Identität oder Berechtigung anfordern.  
  
 Das folgende Beispiel zeigt, wie eine öffentliche Klasse durch den eingeschränkten Zugriff geschützt wird, indem Sie festlegen, dass Aufrufer mit einem bestimmten starken Namen signiert werden müssen. Dieses Beispiel verwendet die <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute> mit einem **Bedarf** für den starken Namen. Aufgabenbasierte Informationen zum Signieren einer Assembly mit einem starken Namen finden Sie [erstellen und Assemblys mit starkem Namen](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md).  
  
```vb  
<StrongNameIdentityPermissionAttribute(SecurityAction.Demand, PublicKey := "…hex…", Name := "App1", Version := "0.0.0.0")>  _  
Public Class Class1  
End Class  
```  
  
```csharp  
[StrongNameIdentityPermissionAttribute(SecurityAction.Demand, PublicKey="…hex…", Name="App1", Version="0.0.0.0")]  
public class Class1  
{  
  
}   
```  
  
## <a name="excluding-classes-and-members-from-use-by-untrusted-code"></a>Ausschließen von Klassen und Membern von der Verwendung durch nicht vertrauenswürdigen Code  
 Verwenden Sie die in diesem Abschnitt gezeigten Deklarationen, um bestimmte Klassen und Methoden sowie Eigenschaften und Ereignisse daran zu hindern, von teilweise vertrauenswürdigem Code verwendet zu werden. Durch die Anwendung dieser Deklarationen auf eine Klasse wenden Sie den Schutz auf ihre gesamten Methoden, Eigenschaften und Ereignisse an. Beachten Sie jedoch, dass sich die deklarative Sicherheit nicht auf den Feldzugriff auswirkt. Beachten Sie außerdem, dass Verknüpfungsaufrufe möglicherweise nur Schutz vor direkten Aufrufern bieten und möglicherweise immer noch anfällig sind für Lockangriffe.  
  
> [!NOTE]
>  In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] wurde ein neues Transparenzmodell eingeführt. Die [Sicherheitstransparenter Code, Ebene 2](../../../docs/framework/misc/security-transparent-code-level-2.md) Modell identifiziert sicheren Code mit der <xref:System.Security.SecurityCriticalAttribute> Attribut. Sicherheitsrelevanter Code erfordert, dass sowohl Aufrufer als auch Erben voll vertrauenswürdig sind. Assemblys, die gemäß den Regeln für die Codezugriffssicherheit von früheren Versionen von .NET Framework ausgeführt werden, können Assemblys der Ebene 2 aufrufen. In diesem Fall werden die sicherheitsrelevanten Attribute für die volle Vertrauenswürdigkeit als Verknüpfungsaufrufe behandelt.  
  
 In Assemblys mit starkem Namen eine [LinkDemand](../../../docs/framework/misc/link-demands.md) gilt für alle öffentlich zugänglichen Methoden, Eigenschaften und Ereignisse, um deren Verwendung auf voll vertrauenswürdige Aufrufer zu beschränken. Um diese Funktion zu deaktivieren, müssen Sie das <xref:System.Security.AllowPartiallyTrustedCallersAttribute>-Attribut anwenden. Daher ist die explizite Markierung von Klassen zum Ausschließen von nicht vertrauenswürdiger Aufrufern nur für nicht signierte Assemblys oder Assemblys mit diesem Attribut erforderlich. Sie können diese Deklarationen verwenden, um eine Teilmenge der darin enthaltenen Typen zu markieren, die nicht für nicht vertrauenswürdige Aufrufer bestimmt sind.  
  
 Die folgenden Beispiele zeigen wie verhindert wird, dass Klassen und Member von nicht vertrauenswürdigem Code verwendet werden.  
  
 Für öffentliche nicht versiegelte Klassen:  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _   
System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
Public Class CanDeriveFromMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public class CanDeriveFromMe  
{  
}  
```  
  
 Für öffentliche versiegelte Klassen:  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
NotInheritable Public Class CannotDeriveFromMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public sealed class CannotDeriveFromMe  
{  
}  
```  
  
 Für öffentliche abstrakte Klassen:  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _  
System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
MustInherit Public Class CannotCreateInstanceOfMe_CanCastToMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public abstract class CannotCreateInstanceOfMe_CanCastToMe {}  
```  
  
 Für öffentliche virtuelle Funktionen:  
  
```vb  
Class Base1   
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Overridable Sub CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe  
End Class 'Base1  
```  
  
```csharp  
class Base1   
{  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
    public virtual void CanOverrideOrCallMe() {}  
}  
```  
  
 Für öffentliche abstrakte Funktionen:  
  
```vb  
MustInherit Class Base2  
    <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Sub MustOverrideMe()  
    End Sub  
End Class 'Base2  
```  
  
```csharp  
abstract class Base2 {  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
public abstract void MustOverrideMe();  
}  
```  
  
 Für öffentliche Funktionen zum Außerkraftsetzen, für deren Basisklasse keine volle Vertrauenswürdigkeit erforderlich ist:  
  
```vb  
Class Derived  
    Inherits Base1  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.Demand, Name:="FullTrust")> _  
    Public Overrides Sub CanOverrideOrCallMe()  
        MyBase.CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe  
End Class 'Derived  
```  
  
```csharp  
class Derived : Base1  
{     
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.Demand, Name="FullTrust")]      
    public override void CanOverrideOrCallMe()   
    {  
        base.CanOverrideOrCallMe();  
    }  
}  
```  
  
 Für öffentliche Funktionen zum Außerkraftsetzen, für deren Basisklasse volle Vertrauenswürdigkeit erforderlich ist:  
  
```vb  
Class Derived  
    Inherits Base1  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Overrides Sub CanOverrideOrCallMe()  
        MyBase.CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe   
End Class 'Derived  
```  
  
```csharp  
class Derived : Base1  
{     
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]      
    public override void CanOverrideOrCallMe()   
    {  
        base.CanOverrideOrCallMe();  
    }  
}  
```  
  
 Für öffentliche Schnittstellen:  
  
```vb  
Public Interface ICanCastToMe  
    <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust")> _  
    Sub CanImplementMe()  
End Interface 'ICanCastToMe  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust")> _  
Class Implemented  
    Implements ICanCastToMe  
    Public Sub CanImplementMe()  
    End Sub 'CanImplementMe  
```  
  
```csharp  
public interface ICanCastToMe   
{  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
void CanImplementMe();  
}  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
class Implemented : ICanCastToMe  
{  
    public void CanImplementMe()  
    {  
    }  
}  
```  
  
## <a name="virtual-internal-overrides-or-overloads-overridable-friend"></a>Überschreibungen von "virtual internal" oder "Overloads Overridable Friend"  
  
> [!NOTE]
>  In diesem Abschnitt zeigt eine Warnung vor einem Sicherheitsproblem beim Deklarieren einer Methode wie `virtual` und `internal` (`Overloads` `Overridable` `Friend` in Visual Basic). Diese Warnung gilt nur für die .NET Framework-Versionen 1.0 und 1.1, sie gelten nicht für höhere Versionen.  
  
 In der .NET Framework-Versionen 1.0 und 1.1 muss Sie ein Merkmal des Typsystemzugriffs Typsystemzugriffs beachten bei der Bestätigung, dass der Code für andere Assemblys nicht verfügbar ist. Eine Methode, die deklariert wird **virtuellen** und **interne** (**Overloads Overridable Friend** in Visual Basic) können Vtable-Eintrag der übergeordneten Klasse überschreiben und kann nur verwendet werden in der gleichen Assembly, da diese intern verfügbar ist. Allerdings wird der Zugriff für die Außerkraftsetzung durch bestimmt die **virtuellen** -Schlüsselwort, und dies kann aus einer anderen Assembly überschrieben werden, solange dieser Code Zugriff auf die Klasse selbst hat. Wenn die Möglichkeit der Außerkraftsetzung ein Problem darstellt, verwenden Sie die deklarative Sicherheit korrigieren oder Entfernen der **virtuellen** Schlüsselwort, wenn es nicht unbedingt erforderlich ist.  
  
 Auch wenn ein Sprachcompiler diese Außerkraftsetzungen durch einen Kompilierungsfehler verhindert, ist die Außerkraftsetzung mithilfe von Code möglich, der mit anderen Compilern geschrieben wurde.  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für das Schreiben von sicherem Code](../../../docs/standard/security/secure-coding-guidelines.md)
