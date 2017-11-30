---
title: x:Property-Anweisung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 618555a8-c893-455c-810f-ac54cd24ef10
caps.latest.revision: "6"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: a59eb23ab3ed6ee6adbbebab0859caffd293b24f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xproperty-directive"></a><span data-ttu-id="bcc56-102">x:Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bcc56-102">x:Property Directive</span></span>
<span data-ttu-id="bcc56-103">Deklariert eine XAML-Eigenschaft in Markup.</span><span class="sxs-lookup"><span data-stu-id="bcc56-103">Declares a XAML property in markup.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="bcc56-104">Verwendung von XAML-Objektelementen</span><span class="sxs-lookup"><span data-stu-id="bcc56-104">XAML Object Element Usage</span></span>  
  
```  
<object x:Class="className">  
  <x:Members>  
    <x:Property Name="propertyName" Type="propertyType/>  
    additionalProperties  
  </x:Members>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="bcc56-105">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="bcc56-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`className`|<span data-ttu-id="bcc56-106">Der Name der Sicherungsklasse oder partiellen Klasse für die XAML-Produktion.</span><span class="sxs-lookup"><span data-stu-id="bcc56-106">Name of the backing class or partial class for the XAML production.</span></span>|  
|`propertyName`|<span data-ttu-id="bcc56-107">Der Membername der Eigenschaft, die definiert wird.</span><span class="sxs-lookup"><span data-stu-id="bcc56-107">Member name of the property being defined.</span></span>|  
|`propertyType`|<span data-ttu-id="bcc56-108">Der Typname (oder eine andere Zeichenfolgenform, frameworkspezifisch), der den Typ dieser Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="bcc56-108">Type name (or other string form, framework-specific) that specifies the type of this property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcc56-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bcc56-109">Remarks</span></span>  
 <span data-ttu-id="bcc56-110">In der .NET Framework-Implementierung der XAML-Dienste</span><span class="sxs-lookup"><span data-stu-id="bcc56-110">In the .NET Framework XAML Services implementation, .</span></span> <span data-ttu-id="bcc56-111">hat `x:Property` keine direkte Typunterstützung, wird jedoch durch die <xref:System.Windows.Markup.PropertyDefinition>-Klasse unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bcc56-111">`x:Property` does not have a direct type backing, but is supported by the <xref:System.Windows.Markup.PropertyDefinition> class.</span></span> <span data-ttu-id="bcc56-112">In einem XAML-Knotenstream wird ein `x:Property`-Element als ein Member namens `Property` aus dem XAML-Namespace der XAML-Sprache dargestellt.</span><span class="sxs-lookup"><span data-stu-id="bcc56-112">In a XAML node stream, an `x:Property` element is represented as a member named `Property`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="bcc56-113">Der Member `Property` enthält Attribute gemäß Deklaration durch Markup.</span><span class="sxs-lookup"><span data-stu-id="bcc56-113">The member `Property` hold attributes as declared by markup.</span></span>  
  
 <span data-ttu-id="bcc56-114">Die Bedeutungen von `Name` und `Type` werden nicht auf der Ebene der .NET Framework-XAML-Dienste zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="bcc56-114">The meaning of `Name` and `Type` are not assigned at the .NET Framework XAML Services level.</span></span> <span data-ttu-id="bcc56-115">Sie sind im ursprünglichen XAML-Knotenstream als Zeichenfolgenwerte gespeichert, um später gemäß den Regeln interpretiert zu werden, die möglicherweise von bestimmten Frameworks erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="bcc56-115">They are stored in the initial XAML node stream as string values, to be interpreted later under the rules that might be imposed by specific frameworks.</span></span> <span data-ttu-id="bcc56-116">Die Bedeutung kann, je nach Implementierung, an der Bedeutung eines XAML-Namens oder eines XAML-Typs ausgerichtet werden oder kann nur in einem Unterstützungstypsystem gültig sein.</span><span class="sxs-lookup"><span data-stu-id="bcc56-116">The meaning might align to a XAML name and XAML type meaning, or might only be valid in a backing type system, depending on the implementation.</span></span>  
  
 <span data-ttu-id="bcc56-117">Damit eine praktische Verwendung von `x:Members` als Mittel zum Angeben von Memberdefinitionen in Markup unterstützt wird, müssen die Member einer Klasse zugeordnet sein, die geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="bcc56-117">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="bcc56-118">Das beabsichtigte Modell besteht darin, dass `x:Members` als ein Member eines Typs vorhanden ist, der eine `x:Class` angibt.</span><span class="sxs-lookup"><span data-stu-id="bcc56-118">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="bcc56-119">Der Mechanismus zum Zuordnen von Typen und Membern oder zum Erstellen von dynamischen Memberdefinitionen wird jedoch auf der Ebene der .NET Framework-XAML-Dienste nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bcc56-119">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at the .NET Framework XAML Services level.</span></span> <span data-ttu-id="bcc56-120">Dies wird von einzelnen Frameworks übernommen, die Anwendungsmodelle haben, die Memberdefinitionen von XAML unterstützen.</span><span class="sxs-lookup"><span data-stu-id="bcc56-120">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="bcc56-121">In der Regel sind, damit dieses Feature unterstützt wird, MSBUILD-Buildvorgänge erforderlich, die XAML als Markup kompilieren und es als CodeBehind integrieren oder reine Von-XAML-Assemblys generieren.</span><span class="sxs-lookup"><span data-stu-id="bcc56-121">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>  
  
## <a name="xproperty-for-windows-workflow-foundation"></a><span data-ttu-id="bcc56-122">x:Property für Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="bcc56-122">x:Property for Windows Workflow Foundation</span></span>  
 <span data-ttu-id="bcc56-123">Für Windows Workflow Foundation definiert `x:Property` die Member einer benutzerdefinierten Aktivität, die vollständig in XAML erstellt ist, oder XAML-definierte dynamische Member für einen Aktivitäts-Designer mit CodeBehind.</span><span class="sxs-lookup"><span data-stu-id="bcc56-123">For Windows Workflow Foundation, `x:Property` defines the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="bcc56-124">`x:Class` muss auch für das Stammelement der XAML-Produktion angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bcc56-124">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="bcc56-125">Dies ist keine Anforderung auf der Ebene der .NET Framework-XAML-Dienste, wird jedoch eine Anforderung, wenn die XAML-Produktion von MSBUILD-Buildvorgängen geladen wird, die benutzerdefinierte Aktivitäten und Windows Workflow Foundation-XAML im Allgemeinen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="bcc56-125">This is not a requirement at the .NET Framework XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="bcc56-126">Windows Workflow Foundation verwendet nicht den reinen XAML-Typnamen als beabsichtigten Wert für die `x:Property` `Type` Attribut, und verwendet stattdessen eine Konvention, die nicht dokumentiert ist hier.</span><span class="sxs-lookup"><span data-stu-id="bcc56-126">Windows Workflow Foundation does not use the pure XAML type name as its intended value for the `x:Property` `Type` attribute, and instead uses a convention that is not documented here.</span></span> <span data-ttu-id="bcc56-127">Weitere Informationen finden Sie unter [DynamicActivity-Erstellung](http://msdn.microsoft.com/library/dd807392.aspx).</span><span class="sxs-lookup"><span data-stu-id="bcc56-127">For more information, see [Dynamic Activity Creation](http://msdn.microsoft.com/library/dd807392.aspx).</span></span>
