---
title: Sichern des Methodenzugriffs
description: Erfahren Sie, wie Sie den Zugriff auf Methoden für Methoden sicher machen, die nicht für die öffentliche Verwendung vorgesehen sind, aber trotzdem öffentlich sein müssen.
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
ms.openlocfilehash: f9b9bc00058aefc8f58facff43509e717967c2a7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555717"
---
# <a name="securing-method-access"></a>Sichern des Methodenzugriffs

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 Einige Methoden sind möglicherweise nicht geeignet, um den Aufruf von beliebigem, nicht vertrauenswürdigen Code zu gestatten. Solche Methoden weisen gewisse Risiken auf: Die Methode bietet möglicherweise eingeschränkte Informationen. Sie akzeptiert evtl. alle an sie übergebenen Informationen. Möglicherweise erfolgt keine Fehlerüberprüfung für die Parameter, oder bei den falschen Parametern können Fehler auftreten oder schädliche Aktionen ausgeführt werden. Sie sollten sich dieser Fälle bewusst sein und Maßnahmen zum Schutz der Methode ergreifen.  
  
 In einigen Fällen müssen Sie Methoden möglicherweise einschränken, die nicht für die öffentliche Verwendung vorgesehen sind, aber dennoch öffentlich sein müssen. Möglicherweise liegt z. B. eine Schnittstelle vor, die zwischen Ihren eigenen DLLs aufgerufen werden muss und daher öffentlich sein muss. Sie möchten sie aber nicht öffentlich verfügbar machen, damit sie weder von Kunden verwendet wird noch bösartigem Code die Gelegenheit bietet, den Einstiegspunkt in Ihre Komponente verfügbar zu machen. Ein weiterer häufiger Grund für die Einschränkung einer Methode, die nicht für die öffentliche Verwendung vorgesehen ist (aber öffentlich sein muss), besteht darin, zu vermeiden, dass eine interne Schnittstelle dokumentiert und unterstützt werden muss.  
  
 Verwalteter Code bietet mehrere Möglichkeiten zum Einschränken des Zugriffs auf Methoden:  
  
- Einschränken des Zugriffsbereichs auf die Klasse, Assembly oder abgeleiteten Klassen, wenn diese vertrauenswürdig sind. Dies ist die einfachste Möglichkeit, um den Methodenzugriff einzuschränken. Im Allgemeinen können abgeleitete Klassen weniger vertrauenswürdig sein als die Klasse, von der Sie abgeleitet sind, obwohl Sie in einigen Fällen die Identität der übergeordneten Klasse gemeinsam nutzen. Sie sollten insbesondere keine Vertrauensstellung vom Schlüsselwort ableiten `protected` , das nicht notwendigerweise im Sicherheitskontext verwendet wird.  
  
- Schränken Sie den Methoden Zugriff auf Aufrufer einer angegebenen Identität ein. im Wesentlichen werden bestimmte [Beweise](/previous-versions/dotnet/netframework-4.0/7y5x1hcd(v=vs.100)) (starker Name, Herausgeber, Zone usw.) ausgewählt.  
  
- Schränken Sie den Methodenzugriff auf Aufrufer mit von Ihnen ausgewählten Berechtigungen ein.  
  
 Die deklarative Sicherheit ermöglicht es Ihnen gleichermaßen, die Vererbung von Klassen zu kontrollieren. Sie können " **vererancedemand** " verwenden, um Folgendes durchzuführen:  
  
- Für abgeleitete Klassen eine bestimmte Identität oder Berechtigung anfordern.  
  
- Für abgeleitete Klassen, die bestimmte Methoden außer Kraft setzen, eine bestimmte Identität oder Berechtigung anfordern.  
  
 Das folgende Beispiel zeigt, wie eine öffentliche Klasse durch den eingeschränkten Zugriff geschützt wird, indem Sie festlegen, dass Aufrufer mit einem bestimmten starken Namen signiert werden müssen. In diesem Beispiel wird die <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute> mit einer **Anforderung** für den starken Namen verwendet. Aufgabenbasierte Informationen zum Signieren einer Assembly mit einem starken Namen finden Sie unter [Erstellen und verwenden](../../standard/assembly/create-use-strong-named.md)von Assemblys mit starkem Namen.  
  
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
 Verwenden Sie die in diesem Abschnitt gezeigten Deklarationen, um bestimmte Klassen und Methoden sowie Eigenschaften und Ereignisse daran zu hindern, von teilweise vertrauenswürdigem Code verwendet zu werden. Indem Sie diese Deklarationen auf eine Klasse anwenden, wenden Sie den Schutz auf alle Methoden, Eigenschaften und Ereignisse an. Der Feld Zugriff wird jedoch von der deklarativen Sicherheit nicht beeinträchtigt. Beachten Sie außerdem, dass Verknüpfungsaufrufe möglicherweise nur Schutz vor direkten Aufrufern bieten und möglicherweise immer noch anfällig sind für Lockangriffe.  
  
> [!NOTE]
> In der .NET Framework 4 wurde ein neues Transparenz Modell eingeführt. Der [Sicherheits transparente Code, das Modell der Ebene 2,](security-transparent-code-level-2.md) identifiziert den sicheren Code mit dem- <xref:System.Security.SecurityCriticalAttribute> Attribut. Sicherheitsrelevanter Code erfordert, dass sowohl Aufrufer als auch Erben voll vertrauenswürdig sind. Assemblys, die gemäß den Regeln für die Codezugriffssicherheit von früheren Versionen von .NET Framework ausgeführt werden, können Assemblys der Ebene 2 aufrufen. In diesem Fall werden die sicherheitsrelevanten Attribute für die volle Vertrauenswürdigkeit als Verknüpfungsaufrufe behandelt.  
  
 In Assemblys mit starkem Namen wird ein [LinkDemand](link-demands.md) auf alle öffentlich zugänglichen Methoden, Eigenschaften und Ereignisse angewendet, um deren Verwendung auf voll vertrauenswürdige Aufrufer einzuschränken. Um diese Funktion zu deaktivieren, müssen Sie das <xref:System.Security.AllowPartiallyTrustedCallersAttribute>-Attribut anwenden. Daher ist die explizite Markierung von Klassen zum Ausschließen von nicht vertrauenswürdiger Aufrufern nur für nicht signierte Assemblys oder Assemblys mit diesem Attribut erforderlich. Sie können diese Deklarationen verwenden, um eine Teilmenge der darin enthaltenen Typen zu markieren, die nicht für nicht vertrauenswürdige Aufrufer bestimmt sind.  
  
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
> In diesem Abschnitt wird vor einem Sicherheitsproblem gewarnt, wenn eine Methode als `virtual` und `internal` ( `Overloads` `Overridable` `Friend` in Visual Basic) deklariert wird. Diese Warnung gilt nur für die .NET Framework Versionen 1,0 und 1,1, Sie gilt nicht für spätere Versionen.  
  
 In den .NET Framework Versionen 1,0 und 1,1 müssen Sie eine Nuance des Typsystem Zugriffs berücksichtigen, wenn Sie bestätigen, dass Ihr Code für andere Assemblys nicht verfügbar ist. Eine Methode, die als " **Virtual** " und " **internal** " (**Overloads Overridable Friend** in Visual Basic) deklariert ist, kann den vtable-Eintrag der übergeordneten Klasse überschreiben und kann nur innerhalb derselben Assembly verwendet werden, da Sie intern ist. Der Zugriff auf das Überschreiben wird jedoch durch das **Virtual** -Schlüsselwort bestimmt und kann von einer anderen Assembly überschrieben werden, solange dieser Code Zugriff auf die Klasse selbst hat. Wenn die Möglichkeit einer außer Kraft Setzung ein Problem darstellt, verwenden Sie die deklarative Sicherheit, um Sie zu beheben, oder entfernen Sie das Schlüsselwort " **Virtual** ", wenn es nicht unbedingt erforderlich ist.  
  
 Selbst wenn ein sprach Compiler diese außer Kraft setzungen aufgrund eines Kompilierungs Fehlers verhindert, kann der Code, der mit anderen Compilern geschrieben wurde, überschreiben.  
  
## <a name="see-also"></a>Weitere Informationen

- [Richtlinien für das Schreiben von sicherem Code](../../standard/security/secure-coding-guidelines.md)
