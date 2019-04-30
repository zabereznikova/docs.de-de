---
title: XamlName-Grammatik
ms.date: 03/30/2017
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
ms.openlocfilehash: 642ca16142bdfe78a40ddf4e6a3a79ce6a8a4985
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938748"
---
# <a name="xamlname-grammar"></a><span data-ttu-id="5f02b-102">XamlName-Grammatik</span><span class="sxs-lookup"><span data-stu-id="5f02b-102">XamlName Grammar</span></span>
<span data-ttu-id="5f02b-103">XamlName-Grammatik ist eine bestimmte Grammatik, die in der XAML-Sprachspezifikation [MS-XAML] definiert ist, die hier der Einfachheit halber reproduziert wird.</span><span class="sxs-lookup"><span data-stu-id="5f02b-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>  
  
## <a name="from-the-xaml-specification"></a><span data-ttu-id="5f02b-104">Der XAML-Spezifikation</span><span class="sxs-lookup"><span data-stu-id="5f02b-104">From the XAML Specification</span></span>  
 <span data-ttu-id="5f02b-105">Die [MS-XAML]-Spezifikation definiert die XamlName-Grammatik zur die zulässigen symbolischen Bezeichner für Typen und Eigenschaften zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5f02b-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>  
  
 <span data-ttu-id="5f02b-106">Zeichenfolgenwerte des Typs, die in der folgenden Grammatik XamlName entsprechen soll:</span><span class="sxs-lookup"><span data-stu-id="5f02b-106">String values that are of type XamlName must conform to the following grammar:</span></span>  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 <span data-ttu-id="5f02b-107">Die die folgenden Werte der allgemeinen Kategorie setzt voraus, wie in der Datenbank der Unicode-Zeichen definiert</span><span class="sxs-lookup"><span data-stu-id="5f02b-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>  
  
```  
Lu  
Letter, Uppercase  
Ll  
Letter, Lowercase  
Lt  
Letter, Titlecase  
Lm  
Letter, Modifier  
Lo  
Letter, Other  
Mn  
Mark, Non-Spacing  
Mc  
Mark, Spacing Combining  
Nd  
Number, Decimal  
Nl  
Number, Letter  
```  
  
 <span data-ttu-id="5f02b-108">XAML definiert, einer zweiten Grammatik, DottedXamlName, die für die Eigenschaft verwendet wird, und Ereignis qualifizierten verweisen, und auch für die angefügte Member.</span><span class="sxs-lookup"><span data-stu-id="5f02b-108">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="5f02b-109">Weitere Informationen finden Sie unter <xref:System.Windows.DependencyProperty> und [XAML Overview (WPF)](../wpf/advanced/xaml-overview-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="5f02b-109">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../wpf/advanced/xaml-overview-wpf.md).</span></span>  
  
 <span data-ttu-id="5f02b-110">Zeichenfolgenwerte des Typs, die in der folgenden Grammatik DottedXamlName entsprechen soll:</span><span class="sxs-lookup"><span data-stu-id="5f02b-110">String values that are of type DottedXamlName must conform to the following grammar:</span></span>  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a><span data-ttu-id="5f02b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5f02b-111">Remarks</span></span>  
 <span data-ttu-id="5f02b-112">Die vollständige Spezifikation finden Sie unter [ \[MS-XAML-\]](https://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="5f02b-112">For the complete specification, see [\[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>
