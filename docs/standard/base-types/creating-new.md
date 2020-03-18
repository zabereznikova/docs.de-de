---
title: Erstellen neuer Zeichenfolgen in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CopyTo method
- Join method
- Format method
- Concat method
- strings [.NET Framework], creating
- Insert method
ms.assetid: 06fdf123-2fac-4459-8904-eb48ab908a30
ms.openlocfilehash: ef65c50111d6ba91ab70d0b9c8cb90c606f9366c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73103820"
---
# <a name="creating-new-strings-in-net"></a><span data-ttu-id="882ca-102">Erstellen neuer Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="882ca-102">Creating New Strings in .NET</span></span>
<span data-ttu-id="882ca-103">.NET Framework ermöglicht das Erstellen von Zeichenfolgen mithilfe einer einfachen Zuweisung und überlädt auch einen Klassenkonstruktor, um die Zeichenfolgenerstellung mithilfe einer Reihe verschiedener Parameter zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="882ca-103">The .NET Framework allows strings to be created using simple assignment, and also overloads a class constructor to support string creation using a number of different parameters.</span></span> <span data-ttu-id="882ca-104">.NET Framework stellt auch verschiedene Methoden in der <xref:System.String?displayProperty=nameWithType>-Klasse bereit, die durch das Kombinieren verschiedener Zeichenfolgen, Zeichenfolgenarrays oder Objekte neue Zeichenfolgenobjekte erstellen.</span><span class="sxs-lookup"><span data-stu-id="882ca-104">The .NET Framework also provides several methods in the <xref:System.String?displayProperty=nameWithType> class that create new string objects by combining several strings, arrays of strings, or objects.</span></span>  
  
## <a name="creating-strings-using-assignment"></a><span data-ttu-id="882ca-105">Erstellen von Zeichenfolgen mithilfe von Zuweisung</span><span class="sxs-lookup"><span data-stu-id="882ca-105">Creating Strings Using Assignment</span></span>  
 <span data-ttu-id="882ca-106">Die einfachste Möglichkeit, ein neues <xref:System.String>-Objekt zu erstellen, ist die Zuweisung eines Zeichenfolgenliterals zu einem <xref:System.String>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="882ca-106">The easiest way to create a new <xref:System.String> object is simply to assign a string literal to a <xref:System.String> object.</span></span>  
  
## <a name="creating-strings-using-a-class-constructor"></a><span data-ttu-id="882ca-107">Erstellen von Zeichenfolgen mithilfe eines Klassenkonstruktors</span><span class="sxs-lookup"><span data-stu-id="882ca-107">Creating Strings Using a Class Constructor</span></span>  
 <span data-ttu-id="882ca-108">Sie können Überladungen des <xref:System.String>-Klassenkonstruktors verwenden, um Zeichenfolgen aus Zeichenarrays zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="882ca-108">You can use overloads of the <xref:System.String> class constructor to create strings from character arrays.</span></span> <span data-ttu-id="882ca-109">Sie können auch eine neue Zeichenfolge erstellen, indem Sie ein bestimmtes Zeichen eine angegebene Anzahl von Malen duplizieren.</span><span class="sxs-lookup"><span data-stu-id="882ca-109">You can also create a new string by duplicating a particular character a specified number of times.</span></span>  
  
## <a name="methods-that-return-strings"></a><span data-ttu-id="882ca-110">Methoden, die Zeichenfolgen zurückgeben</span><span class="sxs-lookup"><span data-stu-id="882ca-110">Methods that Return Strings</span></span>  
 <span data-ttu-id="882ca-111">Die folgende Tabelle führt verschiedene nützliche Methoden auf, die neue Zeichenfolgenobjekte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="882ca-111">The following table lists several useful methods that return new string objects.</span></span>  
  
|<span data-ttu-id="882ca-112">Methodenname</span><span class="sxs-lookup"><span data-stu-id="882ca-112">Method name</span></span>|<span data-ttu-id="882ca-113">Zweck</span><span class="sxs-lookup"><span data-stu-id="882ca-113">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|<span data-ttu-id="882ca-114">Erstellt eine formatierte Zeichenfolge aus einem Satz von Eingabeobjekten.</span><span class="sxs-lookup"><span data-stu-id="882ca-114">Builds a formatted string from a set of input objects.</span></span>|  
|<xref:System.String.Concat%2A?displayProperty=nameWithType>|<span data-ttu-id="882ca-115">Erstellt Zeichenfolgen aus mindestens zwei Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="882ca-115">Builds strings from two or more strings.</span></span>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|<span data-ttu-id="882ca-116">Erstellt eine neue Zeichenfolge durch Kombinieren eines Arrays aus Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="882ca-116">Builds a new string by combining an array of strings.</span></span>|  
|<xref:System.String.Insert%2A?displayProperty=nameWithType>|<span data-ttu-id="882ca-117">Erstellt eine neue Zeichenfolge durch Einfügen einer Zeichenfolge in den angegebenen Index einer vorhandenen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="882ca-117">Builds a new string by inserting a string into the specified index of an existing string.</span></span>|  
|<xref:System.String.CopyTo%2A?displayProperty=nameWithType>|<span data-ttu-id="882ca-118">Kopiert angegebene Zeichen in einer Zeichenfolge in eine bestimmte Position in einem Array aus Zeichen.</span><span class="sxs-lookup"><span data-stu-id="882ca-118">Copies specified characters in a string into a specified position in an array of characters.</span></span>|  
  
### <a name="format"></a><span data-ttu-id="882ca-119">Format</span><span class="sxs-lookup"><span data-stu-id="882ca-119">Format</span></span>  
 <span data-ttu-id="882ca-120">Sie können die **String.Format**-Methode verwenden, um formatierte Zeichenfolgen zu erstellen und Zeichenfolgen zu verketten, die mehrere Objekte darstellen.</span><span class="sxs-lookup"><span data-stu-id="882ca-120">You can use the **String.Format** method to create formatted strings and concatenate strings representing multiple objects.</span></span> <span data-ttu-id="882ca-121">Diese Methode konvertiert automatisch alle übergebenen Objekte in eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="882ca-121">This method automatically converts any passed object into a string.</span></span> <span data-ttu-id="882ca-122">Wenn Ihre Anwendung z.B. dem Benutzer einen **Int32**-Wert und einen **DateTime**-Wert anzeigen soll, können Sie ganz einfach mithilfe der **Format**-Methode eine Zeichenfolge erstellen, um diese Werte darzustellen.</span><span class="sxs-lookup"><span data-stu-id="882ca-122">For example, if your application must display an **Int32** value and a **DateTime** value to the user, you can easily construct a string to represent these values using the **Format** method.</span></span> <span data-ttu-id="882ca-123">Informationen zu den mit dieser Methode verwendeten Formatierungskonventionen finden Sie im Abschnitt [Zusammengesetzte Formatierung](../../../docs/standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="882ca-123">For information about formatting conventions used with this method, see the section on [composite formatting](../../../docs/standard/base-types/composite-formatting.md).</span></span>  
  
 <span data-ttu-id="882ca-124">Das folgende Beispiel verwendet die **Format**-Methode, um eine Zeichenfolge zu erstellen, die eine ganzzahlige Variable verwendet.</span><span class="sxs-lookup"><span data-stu-id="882ca-124">The following example uses the **Format** method to create a string that uses an integer variable.</span></span>  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 <span data-ttu-id="882ca-125">In diesem Beispiel zeigt <xref:System.DateTime.Now%2A?displayProperty=nameWithType> das aktuelle Datum und die aktuelle Uhrzeit so an, wie es von der mit dem aktuellen Thread verknüpften Kultur angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="882ca-125">In this example,<xref:System.DateTime.Now%2A?displayProperty=nameWithType> displays the current date and time in a manner specified by the culture associated with the current thread.</span></span>  
  
### <a name="concat"></a><span data-ttu-id="882ca-126">Concat</span><span class="sxs-lookup"><span data-stu-id="882ca-126">Concat</span></span>  
 <span data-ttu-id="882ca-127">Die **String.Concat**-Methode kann verwendet werden, um ganz einfach aus mindestens zwei vorhandenen Objekten ein neues Zeichenfolgenobjekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="882ca-127">The **String.Concat** method can be used to easily create a new string object from two or more existing objects.</span></span> <span data-ttu-id="882ca-128">Die Methode bietet eine sprachunabhängige Möglichkeit zum Verketten von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="882ca-128">It provides a language-independent way to concatenate strings.</span></span> <span data-ttu-id="882ca-129">Diese Methode akzeptiert alle von **System.Object** abgeleiteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="882ca-129">This method accepts any class that derives from **System.Object**.</span></span> <span data-ttu-id="882ca-130">Das folgende Beispiel erstellt eine Zeichenfolge aus zwei vorhandenen Zeichenfolgenobjekten und einem Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="882ca-130">The following example creates a string from two existing string objects and a separating character.</span></span>  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### <a name="join"></a><span data-ttu-id="882ca-131">Join</span><span class="sxs-lookup"><span data-stu-id="882ca-131">Join</span></span>  
 <span data-ttu-id="882ca-132">Die **String.Join**-Methode erstellt eine neue Zeichenfolge aus einem Array aus Zeichenfolgen und einem Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="882ca-132">The **String.Join** method creates a new string from an array of strings and a separator string.</span></span> <span data-ttu-id="882ca-133">Diese Methode ist nützlich, wenn Sie mehrere Zeichenfolgen miteinander verketten möchten. Sie erstellt eine Liste, die z.B. durch ein Komma getrennt sein kann.</span><span class="sxs-lookup"><span data-stu-id="882ca-133">This method is useful if you want to concatenate multiple strings together, making a list perhaps separated by a comma.</span></span>  
  
 <span data-ttu-id="882ca-134">Das folgende Beispiel verwendet ein Leerzeichen, um ein Zeichenfolgenarray zu binden.</span><span class="sxs-lookup"><span data-stu-id="882ca-134">The following example uses a space to bind a string array.</span></span>  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### <a name="insert"></a><span data-ttu-id="882ca-135">Insert</span><span class="sxs-lookup"><span data-stu-id="882ca-135">Insert</span></span>  
 <span data-ttu-id="882ca-136">Die **String.Insert**-Methode erstellt eine neue Zeichenfolge, indem sie eine Zeichenfolge an einer angegebenen Position in einer anderen Zeichenfolge einfügt.</span><span class="sxs-lookup"><span data-stu-id="882ca-136">The **String.Insert** method creates a new string by inserting a string into a specified position in another string.</span></span> <span data-ttu-id="882ca-137">Diese Methode verwendet einen nullbasierten Index.</span><span class="sxs-lookup"><span data-stu-id="882ca-137">This method uses a zero-based index.</span></span> <span data-ttu-id="882ca-138">Das folgende Beispiel fügt eine Zeichenfolge an der fünften Indexposition von `MyString` ein und erstellt mit diesem Wert eine neue Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="882ca-138">The following example inserts a string into the fifth index position of `MyString` and creates a new string with this value.</span></span>  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### <a name="copyto"></a><span data-ttu-id="882ca-139">CopyTo</span><span class="sxs-lookup"><span data-stu-id="882ca-139">CopyTo</span></span>  
 <span data-ttu-id="882ca-140">Die **String.CopyTo**-Methode kopiert Teile einer Zeichenfolge in ein Zeichenarray.</span><span class="sxs-lookup"><span data-stu-id="882ca-140">The **String.CopyTo** method copies portions of a string into an array of characters.</span></span> <span data-ttu-id="882ca-141">Sie können sowohl den Startindex der Zeichenfolge als auch die Anzahl der zu kopierenden Zeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="882ca-141">You can specify both the beginning index of the string and the number of characters to be copied.</span></span> <span data-ttu-id="882ca-142">Diese Methode akzeptiert den Quellindex, ein Array aus Zeichen, den Zielindex und die Anzahl der zu kopierenden Zeichen.</span><span class="sxs-lookup"><span data-stu-id="882ca-142">This method takes the source index, an array of characters, the destination index, and the number of characters to copy.</span></span> <span data-ttu-id="882ca-143">Alle Indizes sind nullbasiert.</span><span class="sxs-lookup"><span data-stu-id="882ca-143">All indexes are zero-based.</span></span>  
  
 <span data-ttu-id="882ca-144">Das folgende Beispiel verwendet die **CopyTo**-Methode, um die Zeichen des Worts „Hello“ aus einem Zeichenfolgenobjekt in die erste Indexposition eines Zeichenarrays zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="882ca-144">The following example uses the **CopyTo** method to copy the characters of the word "Hello" from a string object to the first index position of an array of characters.</span></span>  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="882ca-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="882ca-145">See also</span></span>

- [<span data-ttu-id="882ca-146">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="882ca-146">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)
- [<span data-ttu-id="882ca-147">Kombinierte Formatierung</span><span class="sxs-lookup"><span data-stu-id="882ca-147">Composite Formatting</span></span>](../../../docs/standard/base-types/composite-formatting.md)
