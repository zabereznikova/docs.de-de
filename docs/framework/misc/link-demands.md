---
title: Verknüpfungsaufrufe
description: Informieren Sie sich über Link Aufrufe, die eine Sicherheitsüberprüfung während der Just-in-time (JIT)-Kompilierung verursachen, und untersuchen Sie nur die sofortige aufrufende Assembly des Codes.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], demands
- demanded permissions
- permissions [.NET Framework], demands
- granting permissions, demands
- code access security, demands
- user demands for permission
- caller security checks
- link demands
ms.assetid: a33fd5f9-2de9-4653-a4f0-d9df25082c4d
ms.openlocfilehash: eaf9ee1bb5cd10c724240bacac014503685a0c8c
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309104"
---
# <a name="link-demands"></a><span data-ttu-id="0fba0-103">Verknüpfungsaufrufe</span><span class="sxs-lookup"><span data-stu-id="0fba0-103">Link Demands</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="0fba0-104">Ein Linkaufruf (Verknüpfungsaufruf) bewirkt eine Sicherheitsüberprüfung während der Just-In-Time-Kompilierung, wobei nur die direkt aufrufende Assembly Ihres Codes überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="0fba0-104">A link demand causes a security check during just-in-time compilation and checks only the immediate calling assembly of your code.</span></span> <span data-ttu-id="0fba0-105">Das Verlinken erfolgt, wenn der Code an einen Typverweis, einschließlich Funktionszeigerverweise und Methodenaufrufe, gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="0fba0-105">Linking occurs when your code is bound to a type reference, including function pointer references and method calls.</span></span> <span data-ttu-id="0fba0-106">Hat die aufrufende Assembly keine ausreichende Berechtigung, Ihren Code zu verlinken, ist der Link unzulässig, und beim Laden und Ausführen des Codes wird eine Laufzeitausnahme ausgelöst. </span><span class="sxs-lookup"><span data-stu-id="0fba0-106">If the calling assembly does not have sufficient permission to link to your code, the link is not allowed and a runtime exception is thrown when the code is loaded and run.</span></span> <span data-ttu-id="0fba0-107">Linkaufrufe können in Klassen, die von Ihrem Code erben, überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="0fba0-107">Link demands can be overridden in classes that inherit from your code.</span></span>  
  
 <span data-ttu-id="0fba0-108">Ein vollständiger Stackwalk wird bei dieser Art von Nachfrage nicht durchgeführt, und der Code ist weiterhin anfällig für Lock Angriffe.</span><span class="sxs-lookup"><span data-stu-id="0fba0-108">A full stack walk is not performed with this type of demand and that your code is still susceptible to luring attacks.</span></span> <span data-ttu-id="0fba0-109">Wenn eine Methode in Assembly a z. b. durch einen Link Aufruf geschützt ist, wird ein direkter Aufrufer in Assembly b basierend auf den Berechtigungen von Assembly b ausgewertet.  Der Link Aufruf wertet jedoch keine Methode in Assembly C aus, wenn er die Methode in Assembly a mithilfe der-Methode in Assembly B indirekt aufruft. Der Link Aufruf gibt nur die Berechtigungen an, die direkte Aufrufer in der unmittelbaren aufrufenden Assembly zum Verknüpfen mit dem Code benötigen.</span><span class="sxs-lookup"><span data-stu-id="0fba0-109">For example, if a method in assembly A is protected by a link demand, a direct caller in assembly B is evaluated based on the permissions of Assembly B.  However, the link demand will not evaluate a method in assembly C if it indirectly calls the method in assembly A using the method in assembly B. The link demand specifies only the permissions direct callers in the immediate calling assembly must have to link to your code.</span></span> <span data-ttu-id="0fba0-110">Er gibt nicht die Berechtigungen an, die alle Aufrufer haben müssen, um Ihren Code auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0fba0-110">It does not specify the permissions all callers must have to run your code.</span></span>  
  
 <span data-ttu-id="0fba0-111">Die Stackwalkmodifizierer <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A> und <xref:System.Security.CodeAccessPermission.PermitOnly%2A> haben keinen Einfluss auf die Auswertung von Linkaufrufen.</span><span class="sxs-lookup"><span data-stu-id="0fba0-111">The <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A>, and <xref:System.Security.CodeAccessPermission.PermitOnly%2A> stack walk modifiers do not affect the evaluation of link demands.</span></span>  <span data-ttu-id="0fba0-112">Da Linkaufrufe keinen Stackwalk ausführen, haben die Stackwalkmodifizierer keinen Einfluss auf Linkaufrufe.</span><span class="sxs-lookup"><span data-stu-id="0fba0-112">Because link demands do not perform a stack walk, the stack walk modifiers have no effect on link demands.</span></span>  
  
 <span data-ttu-id="0fba0-113">Wenn auf eine durch einen Link Aufruf geschützte Methode über [Reflektion](../reflection-and-codedom/reflection.md)zugegriffen wird, überprüft ein Link Aufruf den unmittelbaren Aufrufer des Codes, auf den über Reflektion zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="0fba0-113">If a method protected by a link demand is accessed through [Reflection](../reflection-and-codedom/reflection.md), then a link demand checks the immediate caller of the code accessed through reflection.</span></span> <span data-ttu-id="0fba0-114">Dies gilt sowohl für Methodenerkennungen als auch Methodenaufrufe, die über Reflektion ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0fba0-114">This is true both for method discovery and for method invocation performed using reflection.</span></span> <span data-ttu-id="0fba0-115">Angenommen, Code verwendet Reflektion, um ein-Objekt zurückzugeben, <xref:System.Reflection.MethodInfo> das eine durch einen Link Aufruf geschützte Methode darstellt, und übergibt dieses **MethodInfo** -Objekt dann an einen anderen Code, der das-Objekt verwendet, um die ursprüngliche Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="0fba0-115">For example, suppose code uses reflection to return a <xref:System.Reflection.MethodInfo> object representing a method protected by a link demand and then passes that **MethodInfo** object to some other code that uses the object to invoke the original method.</span></span> <span data-ttu-id="0fba0-116">In diesem Fall erfolgt die Überprüfung des Link Bedarfs zweimal: einmal für den Code, der das **MethodInfo** -Objekt zurückgibt, und einmal für den Code, der es aufruft.</span><span class="sxs-lookup"><span data-stu-id="0fba0-116">In this case, the link demand check occurs twice: once for the code that returns the **MethodInfo** object and once for the code that invokes it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0fba0-117">Ein Linkaufruf, der für einen statischen Klassenkonstruktor durchgeführt wird, schützt diesen Konstruktor nicht, da statische Konstruktoren vom System außerhalb des Codeausführungspfades der Anwendung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0fba0-117">A link demand performed on a static class constructor does not protect the constructor because static constructors are called by the system, outside the application's code execution path.</span></span> <span data-ttu-id="0fba0-118">Dies hat zur Folge, dass ein Linkaufruf, wenn er auf eine ganze Klasse angewendet wird, einen statischen Konstruktor nicht schützen kann, obwohl er der Rest der Klasse schützt.</span><span class="sxs-lookup"><span data-stu-id="0fba0-118">As a result, when a link demand is applied to an entire class, it cannot protect access to a static constructor, although it does protect the rest of the class.</span></span>  
  
 <span data-ttu-id="0fba0-119">Im folgenden Codefragment wird deklarativ angegeben, dass sämtlicher Code mit einer Verlinkung zur `ReadData`-Methode die `CustomPermission`-Berechtigung haben muss.</span><span class="sxs-lookup"><span data-stu-id="0fba0-119">The following code fragment declaratively specifies that any code linking to the `ReadData` method must have the `CustomPermission` permission.</span></span> <span data-ttu-id="0fba0-120">Diese Berechtigung ist eine hypothetische benutzerdefinierte Berechtigung und nicht in .NET Framework vorhanden.</span><span class="sxs-lookup"><span data-stu-id="0fba0-120">This permission is a hypothetical custom permission and does not exist in the .NET Framework.</span></span> <span data-ttu-id="0fba0-121">Die Anforderung erfolgt durch Übergeben eines **SecurityAction. LinkDemand** -Flags an den `CustomPermissionAttribute` .</span><span class="sxs-lookup"><span data-stu-id="0fba0-121">The demand is made by passing a **SecurityAction.LinkDemand** flag to the `CustomPermissionAttribute`.</span></span>  
  
```vb  
<CustomPermissionAttribute(SecurityAction.LinkDemand)> _  
Public Shared Function ReadData() As String  
    ' Access a custom resource.  
End Function
```  
  
```csharp  
[CustomPermissionAttribute(SecurityAction.LinkDemand)]  
public static string ReadData()  
{  
    // Access a custom resource.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="0fba0-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0fba0-122">See also</span></span>

- [<span data-ttu-id="0fba0-123">Attribute</span><span class="sxs-lookup"><span data-stu-id="0fba0-123">Attributes</span></span>](../../standard/attributes/index.md)
- [<span data-ttu-id="0fba0-124">Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="0fba0-124">Code Access Security</span></span>](code-access-security.md)
