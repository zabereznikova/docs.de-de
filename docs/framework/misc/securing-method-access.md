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
ms.openlocfilehash: a9e1226483eaa02dc8dc3dfb741e3df6b2985fbe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181159"
---
# <a name="securing-method-access"></a><span data-ttu-id="ea23b-102">Sichern des Methodenzugriffs</span><span class="sxs-lookup"><span data-stu-id="ea23b-102">Securing Method Access</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="ea23b-103">Einige Methoden sind möglicherweise nicht geeignet, um den Aufruf von beliebigem, nicht vertrauenswürdigen Code zu gestatten.</span><span class="sxs-lookup"><span data-stu-id="ea23b-103">Some methods might not be suitable to allow arbitrary untrusted code to call.</span></span> <span data-ttu-id="ea23b-104">Solche Methoden weisen gewisse Risiken auf: Die Methode bietet möglicherweise eingeschränkte Informationen. Sie akzeptiert evtl. alle an sie übergebenen Informationen. Möglicherweise erfolgt keine Fehlerüberprüfung für die Parameter, oder bei den falschen Parametern können Fehler auftreten oder schädliche Aktionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ea23b-104">Such methods pose several risks: The method might provide some restricted information; it might believe any information passed to it; it might not do error checking on the parameters; or with the wrong parameters, it might malfunction or do something harmful.</span></span> <span data-ttu-id="ea23b-105">Sie sollten sich dieser Fälle bewusst sein und Maßnahmen zum Schutz der Methode ergreifen.</span><span class="sxs-lookup"><span data-stu-id="ea23b-105">You should be aware of these cases and take action to help protect the method.</span></span>  
  
 <span data-ttu-id="ea23b-106">In einigen Fällen müssen Sie Methoden möglicherweise einschränken, die nicht für die öffentliche Verwendung vorgesehen sind, aber dennoch öffentlich sein müssen.</span><span class="sxs-lookup"><span data-stu-id="ea23b-106">In some cases, you might need to restrict methods that are not intended for public use but still must be public.</span></span> <span data-ttu-id="ea23b-107">Möglicherweise liegt z. B. eine Schnittstelle vor, die zwischen Ihren eigenen DLLs aufgerufen werden muss und daher öffentlich sein muss. Sie möchten sie aber nicht öffentlich verfügbar machen, damit sie weder von Kunden verwendet wird noch bösartigem Code die Gelegenheit bietet, den Einstiegspunkt in Ihre Komponente verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="ea23b-107">For example, you might have an interface that needs to be called across your own DLLs and hence must be public, but you do not want to expose it publicly to prevent customers from using it or to prevent malicious code from exploiting the entry point into your component.</span></span> <span data-ttu-id="ea23b-108">Eine anderer häufiger Grund zum Einschränken einer Methode, die nicht für die öffentliche Verwendung vorgesehen ist (jedoch öffentlich sein muss), ist es zu vermeiden, dass diese überaus interne Schnittstelle dokumentiert und unterstützt werden muss.</span><span class="sxs-lookup"><span data-stu-id="ea23b-108">Another common reason to restrict a method not intended for public use (but that must be public) is to avoid having to document and support what might be a very internal interface.</span></span>  
  
 <span data-ttu-id="ea23b-109">Verwalteter Code bietet mehrere Möglichkeiten zum Einschränken des Zugriffs auf Methoden:</span><span class="sxs-lookup"><span data-stu-id="ea23b-109">Managed code offers several ways to restrict method access:</span></span>  
  
- <span data-ttu-id="ea23b-110">Einschränken des Zugriffsbereichs auf die Klasse, Assembly oder abgeleiteten Klassen, wenn diese vertrauenswürdig sind.</span><span class="sxs-lookup"><span data-stu-id="ea23b-110">Limit the scope of accessibility to the class, assembly, or derived classes, if they can be trusted.</span></span> <span data-ttu-id="ea23b-111">Dies ist die einfachste Möglichkeit, um den Methodenzugriff einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="ea23b-111">This is the simplest way to limit method access.</span></span> <span data-ttu-id="ea23b-112">Beachten Sie, dass abgeleitete Klassen im Allgemeinen weniger vertrauenswürdig sind als die Klasse, von der sie abgeleitet wurden, obwohl sie in einigen Fällen die Identität der übergeordneten Klasse teilen.</span><span class="sxs-lookup"><span data-stu-id="ea23b-112">Note that, in general, derived classes can be less trustworthy than the class they derive from, though in some cases they share the parent class's identity.</span></span> <span data-ttu-id="ea23b-113">Insbesondere leiten Sie keine Vertrauensstellung aus dem Schlüsselwort **protected**ab, das nicht unbedingt im Sicherheitskontext verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ea23b-113">In particular, do not infer trust from the keyword **protected**, which is not necessarily used in the security context.</span></span>  
  
- <span data-ttu-id="ea23b-114">Beschränken Sie den Methodenzugriff auf Aufrufer einer angegebenen Identität – im Wesentlichen alle bestimmten [Beweise](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7y5x1hcd%28v=vs.100%29) (starker Name, Herausgeber, Zone usw.), die Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="ea23b-114">Limit the method access to callers of a specified identity--essentially, any particular [evidence](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7y5x1hcd%28v=vs.100%29) (strong name, publisher, zone, and so on) you choose.</span></span>  
  
- <span data-ttu-id="ea23b-115">Schränken Sie den Methodenzugriff auf Aufrufer mit von Ihnen ausgewählten Berechtigungen ein.</span><span class="sxs-lookup"><span data-stu-id="ea23b-115">Limit the method access to callers having whatever permissions you select.</span></span>  
  
 <span data-ttu-id="ea23b-116">Die deklarative Sicherheit ermöglicht es Ihnen gleichermaßen, die Vererbung von Klassen zu kontrollieren.</span><span class="sxs-lookup"><span data-stu-id="ea23b-116">Similarly, declarative security allows you to control inheritance of classes.</span></span> <span data-ttu-id="ea23b-117">Sie können **InheritanceDemand** verwenden, um Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="ea23b-117">You can use **InheritanceDemand** to do the following:</span></span>  
  
- <span data-ttu-id="ea23b-118">Für abgeleitete Klassen eine bestimmte Identität oder Berechtigung anfordern.</span><span class="sxs-lookup"><span data-stu-id="ea23b-118">Require derived classes to have a specified identity or permission.</span></span>  
  
- <span data-ttu-id="ea23b-119">Für abgeleitete Klassen, die bestimmte Methoden außer Kraft setzen, eine bestimmte Identität oder Berechtigung anfordern.</span><span class="sxs-lookup"><span data-stu-id="ea23b-119">Require derived classes that override specific methods to have a specified identity or permission.</span></span>  
  
 <span data-ttu-id="ea23b-120">Das folgende Beispiel zeigt, wie eine öffentliche Klasse durch den eingeschränkten Zugriff geschützt wird, indem Sie festlegen, dass Aufrufer mit einem bestimmten starken Namen signiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ea23b-120">The following example shows how to help protect a public class for limited access by requiring that callers be signed with a particular strong name.</span></span> <span data-ttu-id="ea23b-121">In diesem <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute> Beispiel wird die mit einem **Demand** für den starken Namen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ea23b-121">This example uses the <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute> with a **Demand** for the strong name.</span></span> <span data-ttu-id="ea23b-122">Aufgabenbasierte Informationen zum Signieren einer Assembly mit einem starken Namen finden Sie unter [Erstellen und Verwenden von Assemblys](../../standard/assembly/create-use-strong-named.md)mit starkem Namen .</span><span class="sxs-lookup"><span data-stu-id="ea23b-122">For task-based information on how to sign an assembly with a strong name, see [Creating and Using Strong-Named Assemblies](../../standard/assembly/create-use-strong-named.md).</span></span>  
  
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
  
## <a name="excluding-classes-and-members-from-use-by-untrusted-code"></a><span data-ttu-id="ea23b-123">Ausschließen von Klassen und Membern von der Verwendung durch nicht vertrauenswürdigen Code</span><span class="sxs-lookup"><span data-stu-id="ea23b-123">Excluding Classes and Members from Use by Untrusted Code</span></span>  
 <span data-ttu-id="ea23b-124">Verwenden Sie die in diesem Abschnitt gezeigten Deklarationen, um bestimmte Klassen und Methoden sowie Eigenschaften und Ereignisse daran zu hindern, von teilweise vertrauenswürdigem Code verwendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="ea23b-124">Use the declarations shown in this section to prevent specific classes and methods, as well as properties and events, from being used by partially trusted code.</span></span> <span data-ttu-id="ea23b-125">Durch die Anwendung dieser Deklarationen auf eine Klasse wenden Sie den Schutz auf ihre gesamten Methoden, Eigenschaften und Ereignisse an. Beachten Sie jedoch, dass sich die deklarative Sicherheit nicht auf den Feldzugriff auswirkt.</span><span class="sxs-lookup"><span data-stu-id="ea23b-125">By applying these declarations to a class, you apply the protection to all its methods, properties, and events; however, note that field access is not affected by declarative security.</span></span> <span data-ttu-id="ea23b-126">Beachten Sie außerdem, dass Verknüpfungsaufrufe möglicherweise nur Schutz vor direkten Aufrufern bieten und möglicherweise immer noch anfällig sind für Lockangriffe.</span><span class="sxs-lookup"><span data-stu-id="ea23b-126">Note also that link demands help protect against only the immediate callers and might still be subject to luring attacks.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea23b-127">In .NET Framework 4 wurde ein neues Transparenzmodell eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ea23b-127">A new transparency model has been introduced in the .NET Framework 4.</span></span> <span data-ttu-id="ea23b-128">Das [Modell "Security-Transparent Code, Level 2"](security-transparent-code-level-2.md) identifiziert sicheren Code mit dem <xref:System.Security.SecurityCriticalAttribute> Attribut.</span><span class="sxs-lookup"><span data-stu-id="ea23b-128">The [Security-Transparent Code, Level 2](security-transparent-code-level-2.md) model identifies secure code with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="ea23b-129">Sicherheitsrelevanter Code erfordert, dass sowohl Aufrufer als auch Erben voll vertrauenswürdig sind.</span><span class="sxs-lookup"><span data-stu-id="ea23b-129">Security-critical code requires both callers and inheritors to be fully trusted.</span></span> <span data-ttu-id="ea23b-130">Assemblys, die gemäß den Regeln für die Codezugriffssicherheit von früheren Versionen von .NET Framework ausgeführt werden, können Assemblys der Ebene 2 aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ea23b-130">Assemblies that are running under the code access security rules from earlier .NET Framework versions can call level 2 assemblies.</span></span> <span data-ttu-id="ea23b-131">In diesem Fall werden die sicherheitsrelevanten Attribute für die volle Vertrauenswürdigkeit als Verknüpfungsaufrufe behandelt.</span><span class="sxs-lookup"><span data-stu-id="ea23b-131">In this case, the security-critical attributes will be treated as link demands for full trust.</span></span>  
  
 <span data-ttu-id="ea23b-132">In Assemblys mit starkem Namen wird ein [LinkDemand](link-demands.md) auf alle öffentlich zugänglichen Methoden, Eigenschaften und Ereignisse angewendet, um deren Verwendung auf voll vertrauenswürdige Aufrufer zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="ea23b-132">In strong-named assemblies, a [LinkDemand](link-demands.md) is applied to all publicly accessible methods, properties, and events therein to restrict their use to fully trusted callers.</span></span> <span data-ttu-id="ea23b-133">Um diese Funktion zu deaktivieren, müssen Sie das <xref:System.Security.AllowPartiallyTrustedCallersAttribute>-Attribut anwenden.</span><span class="sxs-lookup"><span data-stu-id="ea23b-133">To disable this feature, you must apply the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="ea23b-134">Daher ist die explizite Markierung von Klassen zum Ausschließen von nicht vertrauenswürdiger Aufrufern nur für nicht signierte Assemblys oder Assemblys mit diesem Attribut erforderlich. Sie können diese Deklarationen verwenden, um eine Teilmenge der darin enthaltenen Typen zu markieren, die nicht für nicht vertrauenswürdige Aufrufer bestimmt sind.</span><span class="sxs-lookup"><span data-stu-id="ea23b-134">Thus, explicitly marking classes to exclude untrusted callers is necessary only for unsigned assemblies or assemblies with this attribute; you can use these declarations to mark a subset of types therein that are not intended for untrusted callers.</span></span>  
  
 <span data-ttu-id="ea23b-135">Die folgenden Beispiele zeigen wie verhindert wird, dass Klassen und Member von nicht vertrauenswürdigem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ea23b-135">The following examples show how to prevent classes and members from being used by untrusted code.</span></span>  
  
 <span data-ttu-id="ea23b-136">Für öffentliche nicht versiegelte Klassen:</span><span class="sxs-lookup"><span data-stu-id="ea23b-136">For public nonsealed classes:</span></span>  
  
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
  
 <span data-ttu-id="ea23b-137">Für öffentliche versiegelte Klassen:</span><span class="sxs-lookup"><span data-stu-id="ea23b-137">For public sealed classes:</span></span>  
  
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
  
 <span data-ttu-id="ea23b-138">Für öffentliche abstrakte Klassen:</span><span class="sxs-lookup"><span data-stu-id="ea23b-138">For public abstract classes:</span></span>  
  
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
  
 <span data-ttu-id="ea23b-139">Für öffentliche virtuelle Funktionen:</span><span class="sxs-lookup"><span data-stu-id="ea23b-139">For public virtual functions:</span></span>  
  
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
  
 <span data-ttu-id="ea23b-140">Für öffentliche abstrakte Funktionen:</span><span class="sxs-lookup"><span data-stu-id="ea23b-140">For public abstract functions:</span></span>  
  
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
  
 <span data-ttu-id="ea23b-141">Für öffentliche Funktionen zum Außerkraftsetzen, für deren Basisklasse keine volle Vertrauenswürdigkeit erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="ea23b-141">For public override functions where the base class does not demand full trust:</span></span>  
  
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
  
 <span data-ttu-id="ea23b-142">Für öffentliche Funktionen zum Außerkraftsetzen, für deren Basisklasse volle Vertrauenswürdigkeit erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="ea23b-142">For public override functions where the base class demands full trust:</span></span>  
  
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
  
 <span data-ttu-id="ea23b-143">Für öffentliche Schnittstellen:</span><span class="sxs-lookup"><span data-stu-id="ea23b-143">For public interfaces:</span></span>  
  
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
  
## <a name="virtual-internal-overrides-or-overloads-overridable-friend"></a><span data-ttu-id="ea23b-144">Überschreibungen von "virtual internal" oder "Overloads Overridable Friend"</span><span class="sxs-lookup"><span data-stu-id="ea23b-144">Virtual Internal Overrides or Overloads Overridable Friend</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea23b-145">In diesem Abschnitt wird vor einem Sicherheitsproblem `virtual` `internal` gewarnt, wenn eine Methode als beide und (in`Overloads` `Overridable` `Friend` Visual Basic) deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="ea23b-145">This section warns about a security issue when declaring a method as both `virtual` and `internal` (`Overloads` `Overridable` `Friend` in Visual Basic).</span></span> <span data-ttu-id="ea23b-146">Diese Warnung gilt nur für die .NET Framework-Versionen 1.0 und 1.1, sie gilt nicht für spätere Versionen.</span><span class="sxs-lookup"><span data-stu-id="ea23b-146">This warning applies only to the .NET Framework versions 1.0 and 1.1, it does not apply to later versions.</span></span>  
  
 <span data-ttu-id="ea23b-147">In den .NET Framework-Versionen 1.0 und 1.1 müssen Sie eine Nuance des Typs Systemzugriff kennen, wenn Sie bestätigen, dass Der Code für andere Assemblys nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ea23b-147">In the .NET Framework versions 1.0 and 1.1, you must be aware of a nuance of the type system accessibility when confirming that your code is unavailable to other assemblies.</span></span> <span data-ttu-id="ea23b-148">Eine Methode, die als **virtuell** und **intern** deklariert ist **(Überladen von überschreibbarem Freund** in Visual Basic) kann den vtable-Eintrag der übergeordneten Klasse überschreiben und kann nur innerhalb derselben Assembly verwendet werden, da sie intern ist.</span><span class="sxs-lookup"><span data-stu-id="ea23b-148">A method that is declared **virtual** and **internal** (**Overloads Overridable Friend** in Visual Basic) can override the parent class's vtable entry and can be used only from within the same assembly because it is internal.</span></span> <span data-ttu-id="ea23b-149">Der Zugriff auf das Überschreiben wird jedoch durch das **virtuelle** Schlüsselwort bestimmt, und dies kann von einer anderen Assembly überschrieben werden, solange dieser Code Zugriff auf die Klasse selbst hat.</span><span class="sxs-lookup"><span data-stu-id="ea23b-149">However, the accessibility for overriding is determined by the **virtual** keyword, and this can be overridden from another assembly as long as that code has access to the class itself.</span></span> <span data-ttu-id="ea23b-150">Wenn die Möglichkeit einer Außerkraftsetzung ein Problem darstellt, verwenden Sie deklarative Sicherheit, um es zu beheben, oder entfernen Sie das **virtuelle** Schlüsselwort, wenn es nicht unbedingt erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ea23b-150">If the possibility of an override presents a problem, use declarative security to fix it, or remove the **virtual** keyword if it is not strictly required.</span></span>  
  
 <span data-ttu-id="ea23b-151">Auch wenn ein Sprachcompiler diese Außerkraftsetzungen durch einen Kompilierungsfehler verhindert, ist die Außerkraftsetzung mithilfe von Code möglich, der mit anderen Compilern geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="ea23b-151">Note that even if a language compiler prevents these overrides with a compilation error, it is possible for code written with other compilers to override.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea23b-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ea23b-152">See also</span></span>

- [<span data-ttu-id="ea23b-153">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="ea23b-153">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
