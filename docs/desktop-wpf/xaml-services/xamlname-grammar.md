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
ms.openlocfilehash: 2fc74990b15caaa9b58e6eea5b0212ea22505674
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433049"
---
# <a name="xamlname-grammar"></a><span data-ttu-id="62c20-102">XamlName-Grammatik</span><span class="sxs-lookup"><span data-stu-id="62c20-102">XamlName Grammar</span></span>

<span data-ttu-id="62c20-103">XamlName Grammar ist eine bestimmte Grammatik, die in der XAML-Sprachspezifikation [MS-XAML] definiert ist, die hier aus Gründen der Benutzerfreundlichkeit wiedergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="62c20-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>

## <a name="from-the-xaml-specification"></a><span data-ttu-id="62c20-104">Aus der XAML-Spezifikation</span><span class="sxs-lookup"><span data-stu-id="62c20-104">From the XAML Specification</span></span>

<span data-ttu-id="62c20-105">Die [MS-XAML]-Spezifikation definiert die Grammatik XamlName, um den Satz von rechtlichen symbolischen Bezeichnern zu identifizieren, die für Typen und Eigenschaften verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="62c20-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>

<span data-ttu-id="62c20-106">Zeichenfolgenwerte vom Typ XamlName müssen der folgenden Grammatik entsprechen:</span><span class="sxs-lookup"><span data-stu-id="62c20-106">String values that are of type XamlName must conform to the following grammar:</span></span>

```xaml
XamlName ::= NameStartChar ( NameChar )*
NameStartChar ::= LetterCharacter | '_'
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl
DecimalDigit ::= UnicodeNd
CombiningCharacter ::= UnicodeMn | UnicodeMc
```

<span data-ttu-id="62c20-107">Dies setzt die folgenden allgemeinen Kategoriewerte voraus, wie in der Unicode-Zeichendatenbank definiert</span><span class="sxs-lookup"><span data-stu-id="62c20-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>

| <span data-ttu-id="62c20-108">Unicode-Kategorie</span><span class="sxs-lookup"><span data-stu-id="62c20-108">Unicode category</span></span>   | <span data-ttu-id="62c20-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="62c20-109">Description</span></span>                   |
|--------------------|-------------------------------|
| <span data-ttu-id="62c20-110">Lu</span><span class="sxs-lookup"><span data-stu-id="62c20-110">Lu</span></span>                 | <span data-ttu-id="62c20-111">Letter, Uppercase (Buchstabe, Großschreibung)</span><span class="sxs-lookup"><span data-stu-id="62c20-111">Letter, Uppercase</span></span>             |
| <span data-ttu-id="62c20-112">Ll</span><span class="sxs-lookup"><span data-stu-id="62c20-112">Ll</span></span>                 | <span data-ttu-id="62c20-113">Letter, Lowercase (Buchstabe, Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="62c20-113">Letter, Lowercase</span></span>             |
| <span data-ttu-id="62c20-114">Lt</span><span class="sxs-lookup"><span data-stu-id="62c20-114">Lt</span></span>                 | <span data-ttu-id="62c20-115">Letter, Titlecase (Buchstabe, großer Anfangsbuchstabe)</span><span class="sxs-lookup"><span data-stu-id="62c20-115">Letter, Titlecase</span></span>             |
| <span data-ttu-id="62c20-116">Lm</span><span class="sxs-lookup"><span data-stu-id="62c20-116">Lm</span></span>                 | <span data-ttu-id="62c20-117">Letter, Modifier (Buchstabe, Modifizierer)</span><span class="sxs-lookup"><span data-stu-id="62c20-117">Letter, Modifier</span></span>              |
| <span data-ttu-id="62c20-118">Lo</span><span class="sxs-lookup"><span data-stu-id="62c20-118">Lo</span></span>                 | <span data-ttu-id="62c20-119">Letter, Other (Buchstabe, andere)</span><span class="sxs-lookup"><span data-stu-id="62c20-119">Letter, Other</span></span>                 |
| <span data-ttu-id="62c20-120">Mn</span><span class="sxs-lookup"><span data-stu-id="62c20-120">Mn</span></span>                 | <span data-ttu-id="62c20-121">Mark, Nicht-Abstand</span><span class="sxs-lookup"><span data-stu-id="62c20-121">Mark, Non-Spacing</span></span>             |
| <span data-ttu-id="62c20-122">Mc</span><span class="sxs-lookup"><span data-stu-id="62c20-122">Mc</span></span>                 | <span data-ttu-id="62c20-123">Mark, Spacing Combining (Satzzeichen, Kombinationszeichen mit Vorschub)</span><span class="sxs-lookup"><span data-stu-id="62c20-123">Mark, Spacing Combining</span></span>       |
| <span data-ttu-id="62c20-124">Nd</span><span class="sxs-lookup"><span data-stu-id="62c20-124">Nd</span></span>                 | <span data-ttu-id="62c20-125">Zahl, Dezimal</span><span class="sxs-lookup"><span data-stu-id="62c20-125">Number, Decimal</span></span>               |
| <span data-ttu-id="62c20-126">Nl</span><span class="sxs-lookup"><span data-stu-id="62c20-126">Nl</span></span>                 | <span data-ttu-id="62c20-127">Number, Letter (Zahl, Buchstabe)</span><span class="sxs-lookup"><span data-stu-id="62c20-127">Number, Letter</span></span>                |

<span data-ttu-id="62c20-128">XAML definiert eine zweite Grammatik, DottedXamlName, die für Eigenschaften- und ereignisqualifizierte Verweise sowie für angefügte Member verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="62c20-128">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="62c20-129">Weitere Informationen finden <xref:System.Windows.DependencyProperty> Sie unter [und XAML-Übersicht (WPF)](../fundamentals/xaml.md).</span><span class="sxs-lookup"><span data-stu-id="62c20-129">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../fundamentals/xaml.md).</span></span>

<span data-ttu-id="62c20-130">Zeichenfolgenwerte vom Typ DottedXamlName müssen der folgenden Grammatik entsprechen:</span><span class="sxs-lookup"><span data-stu-id="62c20-130">String values that are of type DottedXamlName must conform to the following grammar:</span></span>

```xaml
DottedXamlName ::= XamlName '.' XamlName
```

## <a name="remarks"></a><span data-ttu-id="62c20-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="62c20-131">Remarks</span></span>

<span data-ttu-id="62c20-132">Die vollständige Spezifikation finden Sie unter [ \[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="62c20-132">For the complete specification, see [\[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>
