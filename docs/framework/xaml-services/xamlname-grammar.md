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
ms.openlocfilehash: 32fd7b7b952ebbc853e41c0a8276d1ab487e619f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561890"
---
# <a name="xamlname-grammar"></a><span data-ttu-id="91c6b-102">XamlName-Grammatik</span><span class="sxs-lookup"><span data-stu-id="91c6b-102">XamlName Grammar</span></span>
<span data-ttu-id="91c6b-103">XamlName-Grammatik ist eine bestimmte Grammatik, die in der XAML-Sprachspezifikation [MS-XAML] definiert ist, die hier der Einfachheit halber reproduziert werden.</span><span class="sxs-lookup"><span data-stu-id="91c6b-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>  
  
## <a name="from-the-xaml-specification"></a><span data-ttu-id="91c6b-104">Von der Verwendung von XAML-Spezifikation</span><span class="sxs-lookup"><span data-stu-id="91c6b-104">From the XAML Specification</span></span>  
 <span data-ttu-id="91c6b-105">Die [MS-XAML]-Spezifikation definiert die XamlName-Grammatik zur Kennzeichnung der Gruppe der zulässigen symbolischen Bezeichner für Typen und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="91c6b-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>  
  
 <span data-ttu-id="91c6b-106">Zeichenfolgenwerte des Typs XamlName muss in der folgenden Grammatik entsprechen:</span><span class="sxs-lookup"><span data-stu-id="91c6b-106">String values that are of type XamlName must conform to the following grammar:</span></span>  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 <span data-ttu-id="91c6b-107">Die folgenden allgemeinen Kategoriewerte davon ausgeht, gemäß der Definition in der Datenbank der Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="91c6b-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>  
  
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
  
 <span data-ttu-id="91c6b-108">XAML-Code definiert eine zweite Grammatik, DottedXamlName, für die Eigenschaft verwendeten und Ereignis Verweise und auch für angefügte Member an.</span><span class="sxs-lookup"><span data-stu-id="91c6b-108">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="91c6b-109">Weitere Informationen finden Sie unter <xref:System.Windows.DependencyProperty> und [XAML Overview (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="91c6b-109">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).</span></span>  
  
 <span data-ttu-id="91c6b-110">Zeichenfolgenwerte des Typs DottedXamlName muss in der folgenden Grammatik entsprechen:</span><span class="sxs-lookup"><span data-stu-id="91c6b-110">String values that are of type DottedXamlName must conform to the following grammar:</span></span>  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a><span data-ttu-id="91c6b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="91c6b-111">Remarks</span></span>  
 <span data-ttu-id="91c6b-112">Die vollständige Spezifikation finden Sie unter [ \[MS-XAML-\]](http://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="91c6b-112">For the complete specification, see [\[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>
