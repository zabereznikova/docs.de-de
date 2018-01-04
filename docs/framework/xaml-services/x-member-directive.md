---
title: x:Member-Anweisung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d8394ef-644c-4331-b6c5-be855d392980
caps.latest.revision: "5"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4ea04dfe5f3c371acbb388256b0854b0da8f45a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="xmember-directive"></a><span data-ttu-id="70ff5-102">x:Member-Anweisung</span><span class="sxs-lookup"><span data-stu-id="70ff5-102">x:Member Directive</span></span>
<span data-ttu-id="70ff5-103">Deklariert einen XAML-Member im Markup.</span><span class="sxs-lookup"><span data-stu-id="70ff5-103">Declares a XAML member in markup.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="70ff5-104">Verwendung von XAML-Objektelementen</span><span class="sxs-lookup"><span data-stu-id="70ff5-104">XAML Object Element Usage</span></span>  
  
```  
<object x:Class="className">  
  <x:Members>  
    <x:Member Name="propertyName"/>  
    additionalMembers  
  </x:Members>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="70ff5-105">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="70ff5-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`className`|<span data-ttu-id="70ff5-106">Der Name der Sicherungsklasse oder partiellen Klasse für die XAML-Produktion.</span><span class="sxs-lookup"><span data-stu-id="70ff5-106">Name of the backing class or partial class for the XAML production.</span></span>|  
|`memberName`|<span data-ttu-id="70ff5-107">Der Membername der Eigenschaft, die definiert wird.</span><span class="sxs-lookup"><span data-stu-id="70ff5-107">Member name of the property being defined.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70ff5-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="70ff5-108">Remarks</span></span>  
 <span data-ttu-id="70ff5-109">In der .NET Framework-Implementierung der XAML-Dienste</span><span class="sxs-lookup"><span data-stu-id="70ff5-109">In the .NET Framework XAML Services implementation, .</span></span> <span data-ttu-id="70ff5-110">hat `x:Member` keine direkte Typunterstützung, wird jedoch durch die <xref:System.Windows.Markup.MemberDefinition>-Klasse unterstützt.</span><span class="sxs-lookup"><span data-stu-id="70ff5-110">`x:Member` does not have a direct type backing, but is supported by the <xref:System.Windows.Markup.MemberDefinition> class.</span></span> <span data-ttu-id="70ff5-111">In einem XAML-Knotenstream wird ein `x:Member`-Element als ein Member namens `Member` aus dem XAML-Namespace der XAML-Sprache dargestellt.</span><span class="sxs-lookup"><span data-stu-id="70ff5-111">In a XAML node stream, an `x:Member` element is represented as a member named `Member`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="70ff5-112">Der Member `Member` enthält Attribute gemäß Deklaration durch Markup.</span><span class="sxs-lookup"><span data-stu-id="70ff5-112">The member `Member` holds attributes as declared by markup.</span></span>  
  
 <span data-ttu-id="70ff5-113">Die Bedeutungen von `Name` und `Type` werden nicht auf der Ebene der .NET Framework-XAML-Dienste zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="70ff5-113">The meaning of `Name` and `Type` are not assigned at the .NET Framework XAML Services level.</span></span> <span data-ttu-id="70ff5-114">Sie sind im ursprünglichen XAML-Knotenstream als Zeichenfolgenwerte gespeichert, um später gemäß den Regeln interpretiert zu werden, die möglicherweise von bestimmten Frameworks erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="70ff5-114">They are stored in the initial XAML node stream as string values, to be interpreted later under the rules that might be imposed by specific frameworks.</span></span> <span data-ttu-id="70ff5-115">Die Bedeutung kann, je nach Implementierung, an der Bedeutung eines XAML-Namens oder eines XAML-Typs ausgerichtet werden oder kann nur in einem Unterstützungstypsystem gültig sein.</span><span class="sxs-lookup"><span data-stu-id="70ff5-115">The meaning might align to a XAML name and XAML type meaning, or might only be valid in a backing type system, depending on the implementation.</span></span>  
  
 <span data-ttu-id="70ff5-116">Damit eine praktische Verwendung von `x:Members` als Mittel zum Angeben von Memberdefinitionen in Markup unterstützt wird, müssen die Member einer Klasse zugeordnet sein, die geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="70ff5-116">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="70ff5-117">Das beabsichtigte Modell besteht darin, dass `x:Members` als ein Member eines Typs vorhanden ist, der eine `x:Class` angibt.</span><span class="sxs-lookup"><span data-stu-id="70ff5-117">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="70ff5-118">Der Mechanismus zum Zuordnen von Typen und Membern oder zum Erstellen von dynamischen Memberdefinitionen wird jedoch auf der Ebene der .NET Framework-XAML-Dienste nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="70ff5-118">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at the .NET Framework XAML Services level.</span></span> <span data-ttu-id="70ff5-119">Dies wird von einzelnen Frameworks übernommen, die Anwendungsmodelle haben, die Memberdefinitionen von XAML unterstützen.</span><span class="sxs-lookup"><span data-stu-id="70ff5-119">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="70ff5-120">In der Regel sind, damit dieses Feature unterstützt wird, MSBUILD-Buildvorgänge erforderlich, die XAML als Markup kompilieren und es als CodeBehind integrieren oder reine Von-XAML-Assemblys generieren.</span><span class="sxs-lookup"><span data-stu-id="70ff5-120">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>  
  
## <a name="xproperty-for-windows-workflow-foundation"></a><span data-ttu-id="70ff5-121">x:Property für Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="70ff5-121">x:Property for Windows Workflow Foundation</span></span>  
 <span data-ttu-id="70ff5-122">Für Windows Workflow Foundation definiert `x:Property` die Member einer benutzerdefinierten Aktivität, die vollständig in XAML erstellt ist, oder XAML-definierte dynamische Member für einen Aktivitäts-Designer mit CodeBehind.</span><span class="sxs-lookup"><span data-stu-id="70ff5-122">For Windows Workflow Foundation, `x:Property` defines the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="70ff5-123">`x:Class` muss auch für das Stammelement der XAML-Produktion angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="70ff5-123">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="70ff5-124">Dies ist keine Anforderung auf der Ebene der .NET Framework-XAML-Dienste, wird jedoch eine Anforderung, wenn die XAML-Produktion von MSBUILD-Buildvorgängen geladen wird, die benutzerdefinierte Aktivitäten und Windows Workflow Foundation-XAML im Allgemeinen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="70ff5-124">This is not a requirement at the .NET Framework XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="70ff5-125">Windows Workflow Foundation verwendet nicht den reinen XAML-Typnamen als beabsichtigten Wert für die `x:Property` `Type` Attribut, und verwendet stattdessen eine Konvention, die nicht dokumentiert ist hier.</span><span class="sxs-lookup"><span data-stu-id="70ff5-125">Windows Workflow Foundation does not use the pure XAML type name as its intended value for the `x:Property` `Type` attribute, and instead uses a convention that is not documented here.</span></span> <span data-ttu-id="70ff5-126">Weitere Informationen finden Sie unter [DynamicActivity-Erstellung](http://msdn.microsoft.com/library/dd807392.aspx).</span><span class="sxs-lookup"><span data-stu-id="70ff5-126">For more information, see [Dynamic Activity Creation](http://msdn.microsoft.com/library/dd807392.aspx).</span></span>
