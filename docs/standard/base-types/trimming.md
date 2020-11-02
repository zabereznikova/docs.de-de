---
title: Herausnehmen und Entfernen von Zeichen aus Zeichenfolgen in .NET
description: Erfahren Sie, wie Sie Leerzeichen am Anfang oder Ende einer Zeichenfolge kürzen, oder wie Sie eine beliebige Anzahl von Leerzeichen oder Zeichen ab einer angegebenen Position in der Zeichenfolge in .NET entfernen.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strings [.NET], removing characters
- Remove method
- TrimEnd method
- Trim method
- trimming characters
- TrimStart method
- removing characters
ms.assetid: ab248dab-70d4-4413-81c6-542d153fd195
ms.openlocfilehash: d0057d503474f3f6ff886acda3ce1d72fb3ebe21
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888593"
---
# <a name="trimming-and-removing-characters-from-strings-in-net"></a><span data-ttu-id="51890-103">Herausnehmen und Entfernen von Zeichen aus Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="51890-103">Trimming and Removing Characters from Strings in .NET</span></span>
<span data-ttu-id="51890-104">Wenn Sie einen Satz in einzelne Wörter auflösen, erhalten Sie möglicherweise Wörter mit Leerzeichen (auch als Leerräume bezeichnet) auf beiden Seiten des jeweiligen Wortes.</span><span class="sxs-lookup"><span data-stu-id="51890-104">If you are parsing a sentence into individual words, you might end up with words that have blank spaces (also called white spaces) on either end of the word.</span></span> <span data-ttu-id="51890-105">In diesem Fall können Sie eine der Entfernungsmethoden aus der **System.String** -Klasse verwenden, um an einer bestimmten Position der Zeichenfolge eine beliebige Anzahl von Leerzeichen oder anderen Zeichen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="51890-105">In this situation, you can use one of the trim methods in the **System.String** class to remove any number of spaces or other characters from a specified position in the string.</span></span> <span data-ttu-id="51890-106">In der folgenden Tabelle sind die verfügbaren Entfernungsmethoden aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="51890-106">The following table describes the available trim methods.</span></span>  
  
|<span data-ttu-id="51890-107">Methodenname</span><span class="sxs-lookup"><span data-stu-id="51890-107">Method name</span></span>|<span data-ttu-id="51890-108">Verwendung</span><span class="sxs-lookup"><span data-stu-id="51890-108">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.Trim%2A?displayProperty=nameWithType>|<span data-ttu-id="51890-109">Entfernt in einem Zeichenarray angegebene Leerzeichen am Anfang und Ende einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="51890-109">Removes white spaces or characters specified in an array of characters from the beginning and end of a string.</span></span>|  
|<xref:System.String.TrimEnd%2A?displayProperty=nameWithType>|<span data-ttu-id="51890-110">Entfernt in einem Zeichenarray angegebene Zeichen am Ende einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="51890-110">Removes characters specified in an array of characters from the end of a string.</span></span>|  
|<xref:System.String.TrimStart%2A?displayProperty=nameWithType>|<span data-ttu-id="51890-111">Entfernt in einem Zeichenarray angegebene Zeichen am Anfang einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="51890-111">Removes characters specified in an array of characters from the beginning of a string.</span></span>|  
|<xref:System.String.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="51890-112">Entfernt eine festgelegte Anzahl von Zeichen an der angegebenen Indexposition in einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="51890-112">Removes a specified number of characters from a specified index position in a string.</span></span>|  
  
## <a name="trim"></a><span data-ttu-id="51890-113">Trim</span><span class="sxs-lookup"><span data-stu-id="51890-113">Trim</span></span>

 <span data-ttu-id="51890-114">Wie das folgende Beispiel zeigt, lassen sich mit der <xref:System.String.Trim%2A?displayProperty=nameWithType>-Methode Leerzeichen an beiden Enden einer Zeichenfolge auf einfache Weise entfernen.</span><span class="sxs-lookup"><span data-stu-id="51890-114">You can easily remove white spaces from both ends of a string by using the <xref:System.String.Trim%2A?displayProperty=nameWithType> method, as shown in the following example.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#17)]
 [!code-csharp[Conceptual.String.BasicOps#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#17)]
 [!code-vb[Conceptual.String.BasicOps#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#17)]  
  
 <span data-ttu-id="51890-115">Sie können auch Zeichen am Anfang und am Ende einer Zeichenfolge entfernen, die Sie in einem Zeichenarray angeben.</span><span class="sxs-lookup"><span data-stu-id="51890-115">You can also remove characters that you specify in a character array from the beginning and end of a string.</span></span> <span data-ttu-id="51890-116">Im folgenden Beispiel werden Leerzeichen, Punkte und Sternchen entfernt.</span><span class="sxs-lookup"><span data-stu-id="51890-116">The following example removes white-space characters, periods, and asterisks.</span></span>  
  
 [!code-csharp[Conceptual.String.BasicOps#22](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trim2.cs#22)]
 [!code-vb[Conceptual.String.BasicOps#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trim2.vb#22)]  
  
## <a name="trimend"></a><span data-ttu-id="51890-117">TrimEnd</span><span class="sxs-lookup"><span data-stu-id="51890-117">TrimEnd</span></span>

 <span data-ttu-id="51890-118">Mit der **String.TrimEnd** -Methode werden Zeichen am Ende einer Zeichenfolge entfernt, wodurch ein neues Zeichenfolgenobjekt entsteht.</span><span class="sxs-lookup"><span data-stu-id="51890-118">The **String.TrimEnd** method removes characters from the end of a string, creating a new string object.</span></span> <span data-ttu-id="51890-119">An diese Methode wird ein Zeichenarray übergeben, das die zu entfernenden Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="51890-119">An array of characters is passed to this method to specify the characters to be removed.</span></span> <span data-ttu-id="51890-120">Die Reihenfolge der Elemente im Zeichenarray hat keine Auswirkungen auf den Entfernungsvorgang.</span><span class="sxs-lookup"><span data-stu-id="51890-120">The order of the elements in the character array does not affect the trim operation.</span></span> <span data-ttu-id="51890-121">Der Vorgang wird beendet, sobald ein nicht im Array angegebenes Zeichen gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="51890-121">The trim stops when a character not specified in the array is found.</span></span>  
  
 <span data-ttu-id="51890-122">Im folgenden Beispiel werden die letzten Buchstaben einer Zeichenfolge mit der **TrimEnd** -Methode entfernt.</span><span class="sxs-lookup"><span data-stu-id="51890-122">The following example removes the last letters of a string using the **TrimEnd** method.</span></span> <span data-ttu-id="51890-123">In diesem Beispiel werden die Positionen der Zeichen `'r'` und `'W'` vertauscht, um zu veranschaulichen, dass die Reihenfolge der Zeichen im Array keine Rolle spielt.</span><span class="sxs-lookup"><span data-stu-id="51890-123">In this example, the position of the `'r'` character and the `'W'` character are reversed to illustrate that the order of characters in the array does not matter.</span></span> <span data-ttu-id="51890-124">Beachten Sie, dass durch diesen Code das letzte Wort von `MyString` sowie ein Teil des ersten Wortes entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="51890-124">Notice that this code removes the last word of `MyString` plus part of the first.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#18)]
 [!code-csharp[Conceptual.String.BasicOps#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#18)]
 [!code-vb[Conceptual.String.BasicOps#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#18)]  
  
 <span data-ttu-id="51890-125">Durch diesen Code wird `He` auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="51890-125">This code displays `He` to the console.</span></span>  
  
 <span data-ttu-id="51890-126">Im folgenden Beispiel wird das letzte Wort einer Zeichenfolge mit der **TrimEnd** -Methode entfernt.</span><span class="sxs-lookup"><span data-stu-id="51890-126">The following example removes the last word of a string using the **TrimEnd** method.</span></span> <span data-ttu-id="51890-127">Im Code folgt auf das Wort `Hello` ein Komma. Da das Komma im Zeichenarray nicht als zu entfernendes Zeichen angegeben ist, wird der Vorgang beim Komma beendet.</span><span class="sxs-lookup"><span data-stu-id="51890-127">In this code, a comma follows the word `Hello` and, because the comma is not specified in the array of characters to trim, the trim ends at the comma.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#19)]
 [!code-csharp[Conceptual.String.BasicOps#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#19)]
 [!code-vb[Conceptual.String.BasicOps#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#19)]  
  
 <span data-ttu-id="51890-128">Durch diesen Code wird `Hello,` auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="51890-128">This code displays `Hello,` to the console.</span></span>  
  
## <a name="trimstart"></a><span data-ttu-id="51890-129">TrimStart</span><span class="sxs-lookup"><span data-stu-id="51890-129">TrimStart</span></span>

 <span data-ttu-id="51890-130">Die **String.TrimStart** -Methode ist mit der **String.TrimEnd** -Methode vergleichbar, außer dass eine neue Zeichenfolge erstellt wird, indem Zeichen am Anfang eines bestehenden Zeichenfolgenobjekts entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="51890-130">The **String.TrimStart** method is similar to the **String.TrimEnd** method except that it creates a new string by removing characters from the beginning of an existing string object.</span></span> <span data-ttu-id="51890-131">An die **TrimStart** -Methode wird ein Zeichenarray übergeben, das die zu entfernenden Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="51890-131">An array of characters is passed to the **TrimStart** method to specify the characters to be removed.</span></span> <span data-ttu-id="51890-132">Wie bei der **TrimEnd** -Methode hat die Reihenfolge der Elemente im Zeichenarray keine Auswirkungen auf den Entfernungsvorgang.</span><span class="sxs-lookup"><span data-stu-id="51890-132">As with the **TrimEnd** method, the order of the elements in the character array does not affect the trim operation.</span></span> <span data-ttu-id="51890-133">Der Vorgang wird beendet, sobald ein nicht im Array angegebenes Zeichen gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="51890-133">The trim stops when a character not specified in the array is found.</span></span>  
  
 <span data-ttu-id="51890-134">Im folgenden Beispiel wird das erste Wort einer Zeichenfolge entfernt.</span><span class="sxs-lookup"><span data-stu-id="51890-134">The following example removes the first word of a string.</span></span> <span data-ttu-id="51890-135">In diesem Beispiel werden die Positionen der Zeichen `'l'` und `'H'` vertauscht, um zu veranschaulichen, dass die Reihenfolge der Zeichen im Array keine Rolle spielt.</span><span class="sxs-lookup"><span data-stu-id="51890-135">In this example, the position of the `'l'` character and the `'H'` character are reversed to illustrate that the order of characters in the array does not matter.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#20)]
 [!code-csharp[Conceptual.String.BasicOps#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#20)]
 [!code-vb[Conceptual.String.BasicOps#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#20)]  
  
 <span data-ttu-id="51890-136">Durch diesen Code wird `World!` auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="51890-136">This code displays `World!` to the console.</span></span>  
  
## <a name="remove"></a><span data-ttu-id="51890-137">Remove</span><span class="sxs-lookup"><span data-stu-id="51890-137">Remove</span></span>

 <span data-ttu-id="51890-138">Mit der <xref:System.String.Remove%2A?displayProperty=nameWithType>-Methode wird an einer festgelegten Position innerhalb einer bestehenden Zeichenfolge eine festgelegte Anzahl von Zeichen entfernt.</span><span class="sxs-lookup"><span data-stu-id="51890-138">The <xref:System.String.Remove%2A?displayProperty=nameWithType> method removes a specified number of characters that begin at a specified position in an existing string.</span></span> <span data-ttu-id="51890-139">Diese Methode setzt einen nullbasierten Index voraus.</span><span class="sxs-lookup"><span data-stu-id="51890-139">This method assumes a zero-based index.</span></span>  
  
 <span data-ttu-id="51890-140">Im folgenden Beispiel werden ausgehend von der fünften Position des nullbasierten Zeichenfolgenindizes zehn Zeichen aus einer Zeichenfolge entfernt.</span><span class="sxs-lookup"><span data-stu-id="51890-140">The following example removes ten characters from a string beginning at position five of a zero-based index of the string.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#21](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#21)]
 [!code-csharp[Conceptual.String.BasicOps#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#21)]
 [!code-vb[Conceptual.String.BasicOps#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#21)]  
  
## <a name="replace"></a><span data-ttu-id="51890-141">Ersetzen von</span><span class="sxs-lookup"><span data-stu-id="51890-141">Replace</span></span>

 <span data-ttu-id="51890-142">Sie können auch ein bestimmtes Zeichen oder eine Teilzeichenfolge aus einer Zeichenfolge entfernen, indem Sie die <xref:System.String.Replace%28System.String%2CSystem.String%29?displayProperty=nameWithType>-Methode aufrufen und eine leere Zeichenfolge (<xref:System.String.Empty?displayProperty=nameWithType>) zum Ersetzen angeben.</span><span class="sxs-lookup"><span data-stu-id="51890-142">You can also remove a specified character or substring from a string by calling the <xref:System.String.Replace%28System.String%2CSystem.String%29?displayProperty=nameWithType> method and specifying an empty string (<xref:System.String.Empty?displayProperty=nameWithType>) as the replacement.</span></span> <span data-ttu-id="51890-143">Im folgenden Beispiel werden alle Kommas in einer Zeichenfolge entfernt.</span><span class="sxs-lookup"><span data-stu-id="51890-143">The following example removes all commas from a string.</span></span>  
  
 [!code-csharp[Conceptual.String.BasicOps#23](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/replace1.cs#23)]
 [!code-vb[Conceptual.String.BasicOps#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/replace1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="51890-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51890-144">See also</span></span>

- [<span data-ttu-id="51890-145">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="51890-145">Basic String Operations</span></span>](basic-string-operations.md)
