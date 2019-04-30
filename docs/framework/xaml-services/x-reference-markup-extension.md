---
title: x:Reference-Markuperweiterung
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: 960f5c0e4192df72090c1a571dfc2fc5e3fd8ba3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938878"
---
# <a name="xreference-markup-extension"></a><span data-ttu-id="7ba8d-102">x:Reference-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="7ba8d-102">x:Reference Markup Extension</span></span>
<span data-ttu-id="7ba8d-103">Verweist auf eine Instanz, die an anderer Stelle im XAML-Markup deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="7ba8d-103">References an instance that is declared elsewhere in XAML markup.</span></span> <span data-ttu-id="7ba8d-104">Der Verweis bezieht sich auf ein Element des `x:Name`.</span><span class="sxs-lookup"><span data-stu-id="7ba8d-104">The reference refers to an element's `x:Name`.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="7ba8d-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="7ba8d-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Reference instancexName}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="7ba8d-106">Verwendung von XAML-Objektelementen</span><span class="sxs-lookup"><span data-stu-id="7ba8d-106">XAML Object Element Usage</span></span>  
  
```xaml  
<object>  
  <object.property>  
    <x:Reference Name="instancexName"/>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="7ba8d-107">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="7ba8d-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`instancexName`|<span data-ttu-id="7ba8d-108">Die `x:Name` Wert (oder den Wert der <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-Eigenschaft identifiziert) der Instanz auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7ba8d-108">The `x:Name` value (or value of the <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identified property) of the referenced instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ba8d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7ba8d-109">Remarks</span></span>  
 <span data-ttu-id="7ba8d-110">`x:Reference` unterstützt XAML-Sprachebene ein Konzept der Element-Referenz, die andernfalls in bestimmten Frameworks wie WPF implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7ba8d-110">`x:Reference` provides XAML language-level support for an element reference concept that was otherwise implemented in specific frameworks such as WPF.</span></span>  
  
## <a name="xreference-and-wpf"></a><span data-ttu-id="7ba8d-111">X: Reference und WPF</span><span class="sxs-lookup"><span data-stu-id="7ba8d-111">x:Reference and WPF</span></span>  
 <span data-ttu-id="7ba8d-112">In WPF- und XAML 2006, werden die Elementverweise durch das Feature auf Frameworkebene des <xref:System.Windows.Data.Binding.ElementName%2A> Bindung.</span><span class="sxs-lookup"><span data-stu-id="7ba8d-112">In WPF and XAML 2006, element references are addressed by the framework-level feature of <xref:System.Windows.Data.Binding.ElementName%2A> binding.</span></span> <span data-ttu-id="7ba8d-113">Für die meisten WPF-Anwendungen und Szenarien <xref:System.Windows.Data.Binding.ElementName%2A> Bindung sollte weiterhin verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ba8d-113">For most WPF applications and scenarios, <xref:System.Windows.Data.Binding.ElementName%2A> binding should still be used.</span></span> <span data-ttu-id="7ba8d-114">Ausnahmen von dieser allgemeinen Leitfaden können Fälle enthalten, wobei Datenkontext oder andere bereichsüberlegungen, die die Datenbindung nicht unmöglich ist vorhanden sind und Markupkompilierung nicht beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="7ba8d-114">Exceptions to this general guidance might include cases where there are data context or other scoping considerations that make data binding impractical and where markup compilation is not involved.</span></span>  
  
 <span data-ttu-id="7ba8d-115">`x:Reference` in XAML 2009 ist ein Konstrukt definiert werden.</span><span class="sxs-lookup"><span data-stu-id="7ba8d-115">`x:Reference` is a construct defined in XAML 2009.</span></span> <span data-ttu-id="7ba8d-116">In WPF können Sie XAML 2009-Funktionen verwenden, jedoch nur für XAML, das nicht WPF-markupkompiliert ist.</span><span class="sxs-lookup"><span data-stu-id="7ba8d-116">In WPF, you can use XAML 2009 features, but only for XAML that is not WPF markup-compiled.</span></span> <span data-ttu-id="7ba8d-117">Markupkompilierte XAML und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.</span><span class="sxs-lookup"><span data-stu-id="7ba8d-117">Markup-compiled XAML and the BAML form of XAML do not currently support the XAML 2009 language keywords and features.</span></span>
