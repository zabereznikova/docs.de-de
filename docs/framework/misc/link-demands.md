---
title: Verknüpfungsaufrufe
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2ba3172b1a82c0a9f624a49eb63a193dd29faac1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166986"
---
# <a name="link-demands"></a><span data-ttu-id="98384-102">Verknüpfungsaufrufe</span><span class="sxs-lookup"><span data-stu-id="98384-102">Link Demands</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="98384-103">Ein Linkaufruf (Verknüpfungsaufruf) bewirkt eine Sicherheitsüberprüfung während der Just-In-Time-Kompilierung, wobei nur die direkt aufrufende Assembly Ihres Codes überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="98384-103">A link demand causes a security check during just-in-time compilation and checks only the immediate calling assembly of your code.</span></span> <span data-ttu-id="98384-104">Das Verlinken erfolgt, wenn der Code an einen Typverweis, einschließlich Funktionszeigerverweise und Methodenaufrufe, gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="98384-104">Linking occurs when your code is bound to a type reference, including function pointer references and method calls.</span></span> <span data-ttu-id="98384-105">Hat die aufrufende Assembly keine ausreichende Berechtigung, Ihren Code zu verlinken, ist der Link unzulässig, und beim Laden und Ausführen des Codes wird eine Laufzeitausnahme ausgelöst. </span><span class="sxs-lookup"><span data-stu-id="98384-105">If the calling assembly does not have sufficient permission to link to your code, the link is not allowed and a runtime exception is thrown when the code is loaded and run.</span></span> <span data-ttu-id="98384-106">Linkaufrufe können in Klassen, die von Ihrem Code erben, überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="98384-106">Link demands can be overridden in classes that inherit from your code.</span></span>  
  
 <span data-ttu-id="98384-107">Beachten Sie, dass bei diesem Typ von Forderung kein vollständiger Stackwalk durchgeführt wird und der Code weiterhin anfällig für Täuschungsmanöver ist.</span><span class="sxs-lookup"><span data-stu-id="98384-107">Note that a full stack walk is not performed with this type of demand and that your code is still susceptible to luring attacks.</span></span> <span data-ttu-id="98384-108">Z. B. wenn eine Methode in Assembly A durch einen Linkaufruf geschützt ist, wird ein direkter Aufrufer in Assembly B ausgewertet anhand der Berechtigungen von Assembly B.  Der Linkaufruf wertet jedoch keine Methode in Assembly C aus, wenn in der Assembly, die mit der Methode in Assembly b indirekt die-Methode aufgerufen Der Linkaufruf gibt an, dass nur die Berechtigungen leiten, dass der Aufrufer in der unmittelbar aufrufenden Assembly verfügen müssen, um mit Ihrem Code zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="98384-108">For example, if a method in assembly A is protected by a link demand, a direct caller in assembly B is evaluated based on the permissions of Assembly B.  However, the link demand will not evaluate a method in assembly C if it indirectly calls the method in assembly A using the method in assembly B. The link demand specifies only the permissions direct callers in the immediate calling assembly must have to link to your code.</span></span> <span data-ttu-id="98384-109">Er gibt nicht die Berechtigungen an, die alle Aufrufer haben müssen, um Ihren Code auszuführen.</span><span class="sxs-lookup"><span data-stu-id="98384-109">It does not specify the permissions all callers must have to run your code.</span></span>  
  
 <span data-ttu-id="98384-110">Die Stackwalkmodifizierer <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A> und <xref:System.Security.CodeAccessPermission.PermitOnly%2A> haben keinen Einfluss auf die Auswertung von Linkaufrufen.</span><span class="sxs-lookup"><span data-stu-id="98384-110">The <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A>, and <xref:System.Security.CodeAccessPermission.PermitOnly%2A> stack walk modifiers do not affect the evaluation of link demands.</span></span>  <span data-ttu-id="98384-111">Da Linkaufrufe keinen Stackwalk ausführen, haben die Stackwalkmodifizierer keinen Einfluss auf Linkaufrufe.</span><span class="sxs-lookup"><span data-stu-id="98384-111">Because link demands do not perform a stack walk, the stack walk modifiers have no effect on link demands.</span></span>  
  
 <span data-ttu-id="98384-112">Wenn eine durch einen Linkaufruf geschützte Methode, über zugegriffen wird [Reflektion](../../../docs/framework/reflection-and-codedom/reflection.md), und klicken Sie dann ein Linkaufruf den direkten Aufrufer des Codes, auf den über Reflektion überprüft.</span><span class="sxs-lookup"><span data-stu-id="98384-112">If a method protected by a link demand is accessed through [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md), then a link demand checks the immediate caller of the code accessed through reflection.</span></span> <span data-ttu-id="98384-113">Dies gilt sowohl für Methodenerkennungen als auch Methodenaufrufe, die über Reflektion ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="98384-113">This is true both for method discovery and for method invocation performed using reflection.</span></span> <span data-ttu-id="98384-114">Nehmen wir beispielsweise an, die Code unter Verwendung von Reflektion ein <xref:System.Reflection.MethodInfo> -Objekt durch einen Linkaufruf geschützt, eine Methode darstellt, und übergibt, die dann **MethodInfo** Objekt, das einen anderen Code, der das Objekt wird verwendet, um die ursprüngliche Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="98384-114">For example, suppose code uses reflection to return a <xref:System.Reflection.MethodInfo> object representing a method protected by a link demand and then passes that **MethodInfo** object to some other code that uses the object to invoke the original method.</span></span> <span data-ttu-id="98384-115">In diesem Fall die linkaufrufüberprüfung zweimal: einmal für den Code, der gibt die **MethodInfo** -Objekt und einmal für den Code, den sie aufruft.</span><span class="sxs-lookup"><span data-stu-id="98384-115">In this case the link demand check occurs twice: once for the code that returns the **MethodInfo** object and once for the code that invokes it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98384-116">Ein Linkaufruf, der für einen statischen Klassenkonstruktor durchgeführt wird, schützt diesen Konstruktor nicht, da statische Konstruktoren vom System außerhalb des Codeausführungspfades der Anwendung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="98384-116">A link demand performed on a static class constructor does not protect the constructor because static constructors are called by the system, outside the application's code execution path.</span></span> <span data-ttu-id="98384-117">Dies hat zur Folge, dass ein Linkaufruf, wenn er auf eine ganze Klasse angewendet wird, einen statischen Konstruktor nicht schützen kann, obwohl er der Rest der Klasse schützt.</span><span class="sxs-lookup"><span data-stu-id="98384-117">As a result, when a link demand is applied to an entire class, it cannot protect access to a static constructor, although it does protect the rest of the class.</span></span>  
  
 <span data-ttu-id="98384-118">Im folgenden Codefragment wird deklarativ angegeben, dass sämtlicher Code mit einer Verlinkung zur `ReadData`-Methode die `CustomPermission`-Berechtigung haben muss.</span><span class="sxs-lookup"><span data-stu-id="98384-118">The following code fragment declaratively specifies that any code linking to the `ReadData` method must have the `CustomPermission` permission.</span></span> <span data-ttu-id="98384-119">Diese Berechtigung ist eine hypothetische benutzerdefinierte Berechtigung und nicht in .NET Framework vorhanden.</span><span class="sxs-lookup"><span data-stu-id="98384-119">This permission is a hypothetical custom permission and does not exist in the .NET Framework.</span></span> <span data-ttu-id="98384-120">Die Forderung wird vorgenommen, indem Sie übergeben eine **SecurityAction.LinkDemand** flag, das die `CustomPermissionAttribute`.</span><span class="sxs-lookup"><span data-stu-id="98384-120">The demand is made by passing a **SecurityAction.LinkDemand** flag to the `CustomPermissionAttribute`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="98384-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98384-121">See also</span></span>

- [<span data-ttu-id="98384-122">Attribute</span><span class="sxs-lookup"><span data-stu-id="98384-122">Attributes</span></span>](../../../docs/standard/attributes/index.md)
- [<span data-ttu-id="98384-123">Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="98384-123">Code Access Security</span></span>](../../../docs/framework/misc/code-access-security.md)
