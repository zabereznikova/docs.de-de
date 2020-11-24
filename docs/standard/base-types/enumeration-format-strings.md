---
title: Enumerationsformatzeichenfolgen
description: In diesem Artikel erfahren Sie, wie Sie Enumerationsformatzeichenfolgen mithilfe der Methode „Enum.ToString“ in .NET erstellen. Außerdem formatieren Sie numerische Werte, hexadezimale Werte oder Zeichenfolgenwerte von Enumerationsmembern.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- format specifiers, enumeration format strings
- enumeration format strings
- formatting [.NET], enumeration
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
ms.openlocfilehash: 02a12c36e47a82c15c01e578333e1c4465bab142
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829621"
---
# <a name="enumeration-format-strings"></a><span data-ttu-id="b531a-104">Enumerationsformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="b531a-104">Enumeration format strings</span></span>

<span data-ttu-id="b531a-105">Sie können die <xref:System.Enum.ToString%2A?displayProperty=nameWithType>-Methode verwenden, um ein neues Zeichenfolgenobjekt zu erstellen, das den numerischen, den Hexadezimal- oder den Zeichenfolgenwert eines Enumerationsmembers darstellt.</span><span class="sxs-lookup"><span data-stu-id="b531a-105">You can use the <xref:System.Enum.ToString%2A?displayProperty=nameWithType> method to create a new string object that represents the numeric, hexadecimal, or string value of an enumeration member.</span></span> <span data-ttu-id="b531a-106">Diese Methode akzeptiert eine der Enumerationsformatzeichenfolgen, um den Wert anzugeben, der zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="b531a-106">This method takes one of the enumeration formatting strings to specify the value that you want returned.</span></span>

<span data-ttu-id="b531a-107">In den folgenden Abschnitten werden die Enumerationsformatzeichenfolgen sowie die Werte aufgeführt, die diese zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="b531a-107">The following sections list the enumeration formatting strings and the values they return.</span></span> <span data-ttu-id="b531a-108">Bei diesen Formatbezeichnern wird die Groß- und Kleinschreibung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="b531a-108">These format specifiers are not case-sensitive.</span></span>

## <a name="g-or-g"></a><span data-ttu-id="b531a-109">G oder g</span><span class="sxs-lookup"><span data-stu-id="b531a-109">G or g</span></span>

<span data-ttu-id="b531a-110">Zeigt den Enumerationseintrag nach Möglichkeit als Zeichenfolgenwert an, zeigt andernfalls den ganzzahligen Wert der aktuellen Instanz an.</span><span class="sxs-lookup"><span data-stu-id="b531a-110">Displays the enumeration entry as a string value, if possible, and otherwise displays the integer value of the current instance.</span></span> <span data-ttu-id="b531a-111">Wenn die Enumeration mit festgelegtem **Flags**-Attribut definiert ist, werden die Zeichenfolgenwerte jedes gültigen Eintrags miteinander verkettet und durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="b531a-111">If the enumeration is defined with the **Flags** attribute set, the string values of each valid entry are concatenated together, separated by commas.</span></span> <span data-ttu-id="b531a-112">Wenn das **Flags**-Attribut nicht festgelegt ist, wird ein ungültiger Wert als numerischer Eintrag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b531a-112">If the **Flags** attribute is not set, an invalid value is displayed as a numeric entry.</span></span> <span data-ttu-id="b531a-113">Das folgende Beispiel veranschaulicht den Formatbezeichner „G“.</span><span class="sxs-lookup"><span data-stu-id="b531a-113">The following example illustrates the G format specifier.</span></span>

[!code-csharp[Formatting.Enum#1](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)]
[!code-vb[Formatting.Enum#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]

## <a name="f-or-f"></a><span data-ttu-id="b531a-114">F oder f</span><span class="sxs-lookup"><span data-stu-id="b531a-114">F or f</span></span>

<span data-ttu-id="b531a-115">Zeigt den Enumerationseintrag nach Möglichkeit als Zeichenfolgenwert an.</span><span class="sxs-lookup"><span data-stu-id="b531a-115">Displays the enumeration entry as a string value, if possible.</span></span> <span data-ttu-id="b531a-116">Wenn der Wert vollständig als Summe der Einträge in der Enumeration angezeigt werden kann (selbst wenn das **Flags**-Attribut nicht vorhanden ist), werden die Zeichenfolgenwerte jedes gültigen Eintrags miteinander verkettet und durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="b531a-116">If the value can be completely displayed as a summation of the entries in the enumeration (even if the **Flags** attribute is not present), the string values of each valid entry are concatenated together, separated by commas.</span></span> <span data-ttu-id="b531a-117">Wenn der Wert nicht vollständig durch die Enumerationseinträge ermittelt werden kann, wird der Wert als ganzzahliger Wert formatiert.</span><span class="sxs-lookup"><span data-stu-id="b531a-117">If the value cannot be completely determined by the enumeration entries, then the value is formatted as the integer value.</span></span> <span data-ttu-id="b531a-118">Das folgende Beispiel veranschaulicht den Formatbezeichner „F“.</span><span class="sxs-lookup"><span data-stu-id="b531a-118">The following example illustrates the F format specifier.</span></span>

[!code-csharp[Formatting.Enum#2](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)]
[!code-vb[Formatting.Enum#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]

## <a name="d-or-d"></a><span data-ttu-id="b531a-119">D oder d</span><span class="sxs-lookup"><span data-stu-id="b531a-119">D or d</span></span>

<span data-ttu-id="b531a-120">Zeigt den Enumerationseintrag in der kürzestmöglichen Darstellung als ganzzahligen Wert an.</span><span class="sxs-lookup"><span data-stu-id="b531a-120">Displays the enumeration entry as an integer value in the shortest representation possible.</span></span> <span data-ttu-id="b531a-121">Das folgende Beispiel veranschaulicht den Formatbezeichner „D“.</span><span class="sxs-lookup"><span data-stu-id="b531a-121">The following example illustrates the D format specifier.</span></span>

[!code-csharp[Formatting.Enum#3](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)]
[!code-vb[Formatting.Enum#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]

## <a name="x-or-x"></a><span data-ttu-id="b531a-122">X oder x</span><span class="sxs-lookup"><span data-stu-id="b531a-122">X or x</span></span>

<span data-ttu-id="b531a-123">Zeigt den Enumerationseintrag als Hexadezimalwert an.</span><span class="sxs-lookup"><span data-stu-id="b531a-123">Displays the enumeration entry as a hexadecimal value.</span></span> <span data-ttu-id="b531a-124">Der Wert wird ggf. mit führenden Nullen dargestellt, um sicherzustellen, dass die resultierende Zeichenfolge für jedes Byte im [zugrunde liegenden numerischen Typ](xref:System.Enum.GetUnderlyingType%2A) des Enumerationstyps über zwei Zeichen verfügt.</span><span class="sxs-lookup"><span data-stu-id="b531a-124">The value is represented with leading zeros as necessary, to ensure that the result string has two characters for each byte in the enumeration type's [underlying numeric type](xref:System.Enum.GetUnderlyingType%2A).</span></span> <span data-ttu-id="b531a-125">Das folgende Beispiel veranschaulicht den Formatbezeichner „X“.</span><span class="sxs-lookup"><span data-stu-id="b531a-125">The following example illustrates the X format specifier.</span></span> <span data-ttu-id="b531a-126">Der zugrunde liegende Typ sowohl für <xref:System.ConsoleColor> als auch für <xref:System.IO.FileAttributes> in diesem Beispiel ist <xref:System.Int32> oder ein Integertyp mit 32 Bit (bzw. 4 Byte), wodurch eine Ergebniszeichenfolge mit 8 Zeichen erzeugt wird.</span><span class="sxs-lookup"><span data-stu-id="b531a-126">In the example, the underlying type of both <xref:System.ConsoleColor> and <xref:System.IO.FileAttributes> is <xref:System.Int32>, or a 32-bit (or 4-byte) integer, which produces an 8-character result string.</span></span>

[!code-csharp[Formatting.Enum#4](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)]
[!code-vb[Formatting.Enum#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]

## <a name="example"></a><span data-ttu-id="b531a-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b531a-127">Example</span></span>

<span data-ttu-id="b531a-128">Das folgende Beispiel definiert eine Enumeration namens `Colors`, die aus drei Einträgen besteht: `Red`, `Blue` und `Green`.</span><span class="sxs-lookup"><span data-stu-id="b531a-128">The following example defines an enumeration called `Colors` that consists of three entries: `Red`, `Blue`, and `Green`.</span></span>

[!code-csharp[Formatting.Enum#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
[!code-vb[Formatting.Enum#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]

<span data-ttu-id="b531a-129">Nachdem die Enumeration definiert wurde, kann auf folgende Weise eine Instanz deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="b531a-129">After the enumeration is defined, an instance can be declared in the following manner.</span></span>

[!code-csharp[Formatting.Enum#6](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
[!code-vb[Formatting.Enum#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]

<span data-ttu-id="b531a-130">Dann kann die `Color.ToString(System.String)`-Methode verwendet werden, um den Enumerationswert je nach übergebenem Formatbezeichner auf verschiedene Arten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b531a-130">The `Color.ToString(System.String)` method can then be used to display the enumeration value in different ways, depending on the format specifier passed to it.</span></span>

[!code-csharp[Formatting.Enum#7](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
[!code-vb[Formatting.Enum#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]

## <a name="see-also"></a><span data-ttu-id="b531a-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b531a-131">See also</span></span>

- [<span data-ttu-id="b531a-132">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="b531a-132">Formatting Types</span></span>](formatting-types.md)
