---
title: x:Reference-Markuperweiterung
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: f06e259893111a436e5afe2df754c3edee326d54
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432653"
---
# <a name="xreference-markup-extension"></a><span data-ttu-id="f87f9-102">x:Reference-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="f87f9-102">x:Reference Markup Extension</span></span>

<span data-ttu-id="f87f9-103">Verweist auf eine Instanz, die an anderer Stelle im XAML-Markup deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="f87f9-103">References an instance that is declared elsewhere in XAML markup.</span></span> <span data-ttu-id="f87f9-104">Der Verweis bezieht sich `x:Name`auf die .</span><span class="sxs-lookup"><span data-stu-id="f87f9-104">The reference refers to an element's `x:Name`.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="f87f9-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="f87f9-105">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Reference instancexName}" .../>
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="f87f9-106">Verwendung von XAML-Objektelementen</span><span class="sxs-lookup"><span data-stu-id="f87f9-106">XAML Object Element Usage</span></span>

```xaml
<object>
  <object.property>
    <x:Reference Name="instancexName"/>
  </object.property>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="f87f9-107">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="f87f9-107">XAML Values</span></span>

|||
|-|-|
|`instancexName`|<span data-ttu-id="f87f9-108">Der `x:Name` Wert (oder <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>Wert der -identifizierten Eigenschaft) der referenzierten Instanz.</span><span class="sxs-lookup"><span data-stu-id="f87f9-108">The `x:Name` value (or value of the <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identified property) of the referenced instance.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f87f9-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f87f9-109">Remarks</span></span>

<span data-ttu-id="f87f9-110">`x:Reference`bietet XAML-Sprachunterstützung für ein Elementreferenzkonzept, das andernfalls in bestimmten Frameworks wie WPF implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f87f9-110">`x:Reference` provides XAML language-level support for an element reference concept that was otherwise implemented in specific frameworks such as WPF.</span></span>

## <a name="xreference-and-wpf"></a><span data-ttu-id="f87f9-111">x:Referenz und WPF</span><span class="sxs-lookup"><span data-stu-id="f87f9-111">x:Reference and WPF</span></span>

<span data-ttu-id="f87f9-112">In WPF und XAML 2006 werden Elementverweise durch <xref:System.Windows.Data.Binding.ElementName%2A> das Framework-Level-Feature der Bindung adressiert.</span><span class="sxs-lookup"><span data-stu-id="f87f9-112">In WPF and XAML 2006, element references are addressed by the framework-level feature of <xref:System.Windows.Data.Binding.ElementName%2A> binding.</span></span> <span data-ttu-id="f87f9-113">Für die meisten WPF-Anwendungen und -Szenarien sollte weiterhin <xref:System.Windows.Data.Binding.ElementName%2A> die Bindung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f87f9-113">For most WPF applications and scenarios, <xref:System.Windows.Data.Binding.ElementName%2A> binding should still be used.</span></span> <span data-ttu-id="f87f9-114">Ausnahmen von dieser allgemeinen Anleitung können Fälle umfassen, in denen Datenkontexte oder andere Scoping-Überlegungen vorliegen, die die Datenbindung unpraktisch machen und bei denen die Markupkompilierung nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f87f9-114">Exceptions to this general guidance might include cases where there are data context or other scoping considerations that make data binding impractical and where markup compilation is not involved.</span></span>

<span data-ttu-id="f87f9-115">`x:Reference`ist ein in XAML 2009 definiertes Konstrukt.</span><span class="sxs-lookup"><span data-stu-id="f87f9-115">`x:Reference` is a construct defined in XAML 2009.</span></span> <span data-ttu-id="f87f9-116">In WPF können Sie XAML 2009-Funktionen verwenden, jedoch nur für XAML, das nicht WPF-markupkompiliert ist.</span><span class="sxs-lookup"><span data-stu-id="f87f9-116">In WPF, you can use XAML 2009 features, but only for XAML that is not WPF markup-compiled.</span></span> <span data-ttu-id="f87f9-117">Markupkompilierte XAML und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.</span><span class="sxs-lookup"><span data-stu-id="f87f9-117">Markup-compiled XAML and the BAML form of XAML do not currently support the XAML 2009 language keywords and features.</span></span>
