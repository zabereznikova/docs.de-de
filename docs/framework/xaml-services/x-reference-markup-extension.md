---
title: x:Reference-Markuperweiterung
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: 960f5c0e4192df72090c1a571dfc2fc5e3fd8ba3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562244"
---
# <a name="xreference-markup-extension"></a><span data-ttu-id="2f290-102">x:Reference-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="2f290-102">x:Reference Markup Extension</span></span>
<span data-ttu-id="2f290-103">Verweist auf eine Instanz, die an anderer Stelle im XAML-Markup deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="2f290-103">References an instance that is declared elsewhere in XAML markup.</span></span> <span data-ttu-id="2f290-104">Der Verweis auf ein Element verweist `x:Name`.</span><span class="sxs-lookup"><span data-stu-id="2f290-104">The reference refers to an element's `x:Name`.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="2f290-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="2f290-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Reference instancexName}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="2f290-106">Verwendung von XAML-Objektelementen</span><span class="sxs-lookup"><span data-stu-id="2f290-106">XAML Object Element Usage</span></span>  
  
```xaml  
<object>  
  <object.property>  
    <x:Reference Name="instancexName"/>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="2f290-107">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="2f290-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`instancexName`|<span data-ttu-id="2f290-108">Die `x:Name` Wert (oder des Werts der <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-Eigenschaft identifiziert) der Instanz auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2f290-108">The `x:Name` value (or value of the <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identified property) of the referenced instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f290-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2f290-109">Remarks</span></span>  
 <span data-ttu-id="2f290-110">`x:Reference` bietet Unterstützung für XAML-Sprachebene für ein Konzept der Element-Referenz, die andernfalls in bestimmten Frameworks wie z. B. WPF implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2f290-110">`x:Reference` provides XAML language-level support for an element reference concept that was otherwise implemented in specific frameworks such as WPF.</span></span>  
  
## <a name="xreference-and-wpf"></a><span data-ttu-id="2f290-111">X: Reference-als auch für WPF</span><span class="sxs-lookup"><span data-stu-id="2f290-111">x:Reference and WPF</span></span>  
 <span data-ttu-id="2f290-112">In WPF und XAML 2006 können Elementverweise adressiert werden, indem die Frameworkebene-Funktion von <xref:System.Windows.Data.Binding.ElementName%2A> Bindung.</span><span class="sxs-lookup"><span data-stu-id="2f290-112">In WPF and XAML 2006, element references are addressed by the framework-level feature of <xref:System.Windows.Data.Binding.ElementName%2A> binding.</span></span> <span data-ttu-id="2f290-113">Für die meisten WPF-Anwendungen und Szenarien <xref:System.Windows.Data.Binding.ElementName%2A> Bindung sollte weiterhin verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2f290-113">For most WPF applications and scenarios, <xref:System.Windows.Data.Binding.ElementName%2A> binding should still be used.</span></span> <span data-ttu-id="2f290-114">Ausnahmen von dieser allgemeinen Leitfaden möglicherweise Fällen gehört der, in denen Datenkontext oder andere Bereichsdefinition Aspekte, die die Datenbindung alleine nicht durchführbar vornehmen vorhanden sind und nicht Markupkompilierung beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="2f290-114">Exceptions to this general guidance might include cases where there are data context or other scoping considerations that make data binding impractical and where markup compilation is not involved.</span></span>  
  
 <span data-ttu-id="2f290-115">`x:Reference` in XAML 2009 ist ein Konstrukt definiert werden.</span><span class="sxs-lookup"><span data-stu-id="2f290-115">`x:Reference` is a construct defined in XAML 2009.</span></span> <span data-ttu-id="2f290-116">In WPF können Sie XAML 2009-Funktionen verwenden, jedoch nur für XAML, das nicht WPF-markupkompiliert ist.</span><span class="sxs-lookup"><span data-stu-id="2f290-116">In WPF, you can use XAML 2009 features, but only for XAML that is not WPF markup-compiled.</span></span> <span data-ttu-id="2f290-117">Markupkompilierte XAML und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.</span><span class="sxs-lookup"><span data-stu-id="2f290-117">Markup-compiled XAML and the BAML form of XAML do not currently support the XAML 2009 language keywords and features.</span></span>
