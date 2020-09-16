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
ms.openlocfilehash: ceb027938b6d4313babbe02949e0b6dd5ee85589
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556693"
---
# <a name="xamlname-grammar"></a><span data-ttu-id="ccf23-102">XamlName-Grammatik</span><span class="sxs-lookup"><span data-stu-id="ccf23-102">XamlName Grammar</span></span>

<span data-ttu-id="ccf23-103">Die XamlName-Grammatik ist eine bestimmte Grammatik, die in der XAML-Sprachspezifikation [MS-XAML] definiert ist, die zur einfacheren Wiedergabe hier reproduziert wird.</span><span class="sxs-lookup"><span data-stu-id="ccf23-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>

## <a name="from-the-xaml-specification"></a><span data-ttu-id="ccf23-104">Aus der XAML-Spezifikation</span><span class="sxs-lookup"><span data-stu-id="ccf23-104">From the XAML Specification</span></span>

<span data-ttu-id="ccf23-105">Die [MS-XAML]-Spezifikation definiert den Grammatik-XamlName, um den Satz von juristischen symbolischen bezeichmern zu identifizieren, die für Typen und Eigenschaften verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ccf23-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>

<span data-ttu-id="ccf23-106">Zeichen folgen Werte vom Typ XamlName müssen der folgenden Grammatik entsprechen:</span><span class="sxs-lookup"><span data-stu-id="ccf23-106">String values that are of type XamlName must conform to the following grammar:</span></span>

```xaml
XamlName ::= NameStartChar ( NameChar )*
NameStartChar ::= LetterCharacter | '_'
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl
DecimalDigit ::= UnicodeNd
CombiningCharacter ::= UnicodeMn | UnicodeMc
```

<span data-ttu-id="ccf23-107">Dabei werden die folgenden allgemeinen Kategoriewerte angenommen, wie in der Unicode-Zeichen Datenbank definiert.</span><span class="sxs-lookup"><span data-stu-id="ccf23-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>

| <span data-ttu-id="ccf23-108">Unicode-Kategorie</span><span class="sxs-lookup"><span data-stu-id="ccf23-108">Unicode category</span></span>   | <span data-ttu-id="ccf23-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ccf23-109">Description</span></span>                   |
|--------------------|-------------------------------|
| <span data-ttu-id="ccf23-110">Lu</span><span class="sxs-lookup"><span data-stu-id="ccf23-110">Lu</span></span>                 | <span data-ttu-id="ccf23-111">Letter, Uppercase (Buchstabe, Großschreibung)</span><span class="sxs-lookup"><span data-stu-id="ccf23-111">Letter, Uppercase</span></span>             |
| <span data-ttu-id="ccf23-112">Ll</span><span class="sxs-lookup"><span data-stu-id="ccf23-112">Ll</span></span>                 | <span data-ttu-id="ccf23-113">Letter, Lowercase (Buchstabe, Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="ccf23-113">Letter, Lowercase</span></span>             |
| <span data-ttu-id="ccf23-114">Lt</span><span class="sxs-lookup"><span data-stu-id="ccf23-114">Lt</span></span>                 | <span data-ttu-id="ccf23-115">Letter, Titlecase (Buchstabe, großer Anfangsbuchstabe)</span><span class="sxs-lookup"><span data-stu-id="ccf23-115">Letter, Titlecase</span></span>             |
| <span data-ttu-id="ccf23-116">Lm</span><span class="sxs-lookup"><span data-stu-id="ccf23-116">Lm</span></span>                 | <span data-ttu-id="ccf23-117">Letter, Modifier (Buchstabe, Modifizierer)</span><span class="sxs-lookup"><span data-stu-id="ccf23-117">Letter, Modifier</span></span>              |
| <span data-ttu-id="ccf23-118">Lo</span><span class="sxs-lookup"><span data-stu-id="ccf23-118">Lo</span></span>                 | <span data-ttu-id="ccf23-119">Letter, Other (Buchstabe, andere)</span><span class="sxs-lookup"><span data-stu-id="ccf23-119">Letter, Other</span></span>                 |
| <span data-ttu-id="ccf23-120">Mn</span><span class="sxs-lookup"><span data-stu-id="ccf23-120">Mn</span></span>                 | <span data-ttu-id="ccf23-121">Markierung, nicht Abstand</span><span class="sxs-lookup"><span data-stu-id="ccf23-121">Mark, Non-Spacing</span></span>             |
| <span data-ttu-id="ccf23-122">Mc</span><span class="sxs-lookup"><span data-stu-id="ccf23-122">Mc</span></span>                 | <span data-ttu-id="ccf23-123">Mark, Spacing Combining (Satzzeichen, Kombinationszeichen mit Vorschub)</span><span class="sxs-lookup"><span data-stu-id="ccf23-123">Mark, Spacing Combining</span></span>       |
| <span data-ttu-id="ccf23-124">Nd</span><span class="sxs-lookup"><span data-stu-id="ccf23-124">Nd</span></span>                 | <span data-ttu-id="ccf23-125">Zahl, Decimal</span><span class="sxs-lookup"><span data-stu-id="ccf23-125">Number, Decimal</span></span>               |
| <span data-ttu-id="ccf23-126">Nl</span><span class="sxs-lookup"><span data-stu-id="ccf23-126">Nl</span></span>                 | <span data-ttu-id="ccf23-127">Number, Letter (Zahl, Buchstabe)</span><span class="sxs-lookup"><span data-stu-id="ccf23-127">Number, Letter</span></span>                |

<span data-ttu-id="ccf23-128">XAML definiert eine zweite Grammatik (DottedXamlName), die für Eigenschafts-und Ereignis qualifizierte Verweise und auch für angefügte Member verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ccf23-128">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="ccf23-129">Weitere Informationen finden Sie unter <xref:System.Windows.DependencyProperty> und [Übersicht über XAML (WPF)](../fundamentals/xaml.md).</span><span class="sxs-lookup"><span data-stu-id="ccf23-129">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../fundamentals/xaml.md).</span></span>

<span data-ttu-id="ccf23-130">Zeichen folgen Werte vom Typ "DottedXamlName" müssen der folgenden Grammatik entsprechen:</span><span class="sxs-lookup"><span data-stu-id="ccf23-130">String values that are of type DottedXamlName must conform to the following grammar:</span></span>

```xaml
DottedXamlName ::= XamlName '.' XamlName
```

## <a name="remarks"></a><span data-ttu-id="ccf23-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ccf23-131">Remarks</span></span>

<span data-ttu-id="ccf23-132">Die vollständige Spezifikation finden Sie unter [ \[ MS-XAML \] ](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="ccf23-132">For the complete specification, see [\[MS-XAML\]](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>
