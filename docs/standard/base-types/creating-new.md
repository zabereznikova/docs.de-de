---
title: Erstellen neuer Zeichenfolgen in .NET
description: Informationen zum Erstellen von Zeichenfolgen mithilfe von Zuweisungen, Klassenkonstruktoren oder System.String-Methoden, die mehrere Zeichenfolgen, Arrays von Zeichenfolgen oder Objekte in .NET kombinieren
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CopyTo method
- Join method
- Format method
- Concat method
- strings [.NET], creating
- Insert method
ms.assetid: 06fdf123-2fac-4459-8904-eb48ab908a30
ms.openlocfilehash: a00274b7b6b7e7a54d8546f2176109688a4c4678
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824882"
---
# <a name="creating-new-strings-in-net"></a><span data-ttu-id="9a53b-103">Erstellen neuer Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="9a53b-103">Creating New Strings in .NET</span></span>

<span data-ttu-id="9a53b-104">.NET ermöglicht das Erstellen von Zeichenfolgen mithilfe einer einfachen Zuweisung und überlädt auch einen Klassenkonstruktor, um die Zeichenfolgenerstellung mithilfe von verschiedenen Parametern zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9a53b-104">.NET allows strings to be created using simple assignment, and also overloads a class constructor to support string creation using a number of different parameters.</span></span> <span data-ttu-id="9a53b-105">.NET stellt auch verschiedene Methoden in der Klasse <xref:System.String?displayProperty=nameWithType> bereit, die durch Kombinieren verschiedener Zeichenfolgen, Zeichenfolgenarrays oder Objekte neue Zeichenfolgenobjekte erstellen.</span><span class="sxs-lookup"><span data-stu-id="9a53b-105">.NET also provides several methods in the <xref:System.String?displayProperty=nameWithType> class that create new string objects by combining several strings, arrays of strings, or objects.</span></span>  
  
## <a name="creating-strings-using-assignment"></a><span data-ttu-id="9a53b-106">Erstellen von Zeichenfolgen mithilfe von Zuweisung</span><span class="sxs-lookup"><span data-stu-id="9a53b-106">Creating Strings Using Assignment</span></span>  
 <span data-ttu-id="9a53b-107">Die einfachste Möglichkeit, ein neues <xref:System.String>-Objekt zu erstellen, ist die Zuweisung eines Zeichenfolgenliterals zu einem <xref:System.String>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="9a53b-107">The easiest way to create a new <xref:System.String> object is simply to assign a string literal to a <xref:System.String> object.</span></span>  
  
## <a name="creating-strings-using-a-class-constructor"></a><span data-ttu-id="9a53b-108">Erstellen von Zeichenfolgen mithilfe eines Klassenkonstruktors</span><span class="sxs-lookup"><span data-stu-id="9a53b-108">Creating Strings Using a Class Constructor</span></span>  
 <span data-ttu-id="9a53b-109">Sie können Überladungen des <xref:System.String>-Klassenkonstruktors verwenden, um Zeichenfolgen aus Zeichenarrays zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9a53b-109">You can use overloads of the <xref:System.String> class constructor to create strings from character arrays.</span></span> <span data-ttu-id="9a53b-110">Sie können auch eine neue Zeichenfolge erstellen, indem Sie ein bestimmtes Zeichen eine angegebene Anzahl von Malen duplizieren.</span><span class="sxs-lookup"><span data-stu-id="9a53b-110">You can also create a new string by duplicating a particular character a specified number of times.</span></span>  
  
## <a name="methods-that-return-strings"></a><span data-ttu-id="9a53b-111">Methoden, die Zeichenfolgen zurückgeben</span><span class="sxs-lookup"><span data-stu-id="9a53b-111">Methods that Return Strings</span></span>  
 <span data-ttu-id="9a53b-112">Die folgende Tabelle führt verschiedene nützliche Methoden auf, die neue Zeichenfolgenobjekte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="9a53b-112">The following table lists several useful methods that return new string objects.</span></span>  
  
|<span data-ttu-id="9a53b-113">Methodenname</span><span class="sxs-lookup"><span data-stu-id="9a53b-113">Method name</span></span>|<span data-ttu-id="9a53b-114">Verwendung</span><span class="sxs-lookup"><span data-stu-id="9a53b-114">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|<span data-ttu-id="9a53b-115">Erstellt eine formatierte Zeichenfolge aus einem Satz von Eingabeobjekten.</span><span class="sxs-lookup"><span data-stu-id="9a53b-115">Builds a formatted string from a set of input objects.</span></span>|  
|<xref:System.String.Concat%2A?displayProperty=nameWithType>|<span data-ttu-id="9a53b-116">Erstellt Zeichenfolgen aus mindestens zwei Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="9a53b-116">Builds strings from two or more strings.</span></span>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|<span data-ttu-id="9a53b-117">Erstellt eine neue Zeichenfolge durch Kombinieren eines Arrays aus Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="9a53b-117">Builds a new string by combining an array of strings.</span></span>|  
|<xref:System.String.Insert%2A?displayProperty=nameWithType>|<span data-ttu-id="9a53b-118">Erstellt eine neue Zeichenfolge durch Einfügen einer Zeichenfolge in den angegebenen Index einer vorhandenen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9a53b-118">Builds a new string by inserting a string into the specified index of an existing string.</span></span>|  
|<xref:System.String.CopyTo%2A?displayProperty=nameWithType>|<span data-ttu-id="9a53b-119">Kopiert angegebene Zeichen in einer Zeichenfolge in eine bestimmte Position in einem Array aus Zeichen.</span><span class="sxs-lookup"><span data-stu-id="9a53b-119">Copies specified characters in a string into a specified position in an array of characters.</span></span>|  
  
### <a name="format"></a><span data-ttu-id="9a53b-120">Format</span><span class="sxs-lookup"><span data-stu-id="9a53b-120">Format</span></span>  
 <span data-ttu-id="9a53b-121">Sie können die **String.Format**-Methode verwenden, um formatierte Zeichenfolgen zu erstellen und Zeichenfolgen zu verketten, die mehrere Objekte darstellen.</span><span class="sxs-lookup"><span data-stu-id="9a53b-121">You can use the **String.Format** method to create formatted strings and concatenate strings representing multiple objects.</span></span> <span data-ttu-id="9a53b-122">Diese Methode konvertiert automatisch alle übergebenen Objekte in eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9a53b-122">This method automatically converts any passed object into a string.</span></span> <span data-ttu-id="9a53b-123">Wenn Ihre Anwendung z.B. dem Benutzer einen **Int32**-Wert und einen **DateTime**-Wert anzeigen soll, können Sie ganz einfach mithilfe der **Format**-Methode eine Zeichenfolge erstellen, um diese Werte darzustellen.</span><span class="sxs-lookup"><span data-stu-id="9a53b-123">For example, if your application must display an **Int32** value and a **DateTime** value to the user, you can easily construct a string to represent these values using the **Format** method.</span></span> <span data-ttu-id="9a53b-124">Informationen zu den mit dieser Methode verwendeten Formatierungskonventionen finden Sie im Abschnitt [Zusammengesetzte Formatierung](composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="9a53b-124">For information about formatting conventions used with this method, see the section on [composite formatting](composite-formatting.md).</span></span>  
  
 <span data-ttu-id="9a53b-125">Das folgende Beispiel verwendet die **Format**-Methode, um eine Zeichenfolge zu erstellen, die eine ganzzahlige Variable verwendet.</span><span class="sxs-lookup"><span data-stu-id="9a53b-125">The following example uses the **Format** method to create a string that uses an integer variable.</span></span>  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 <span data-ttu-id="9a53b-126">In diesem Beispiel zeigt <xref:System.DateTime.Now%2A?displayProperty=nameWithType> das aktuelle Datum und die aktuelle Uhrzeit so an, wie es von der mit dem aktuellen Thread verknüpften Kultur angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="9a53b-126">In this example,<xref:System.DateTime.Now%2A?displayProperty=nameWithType> displays the current date and time in a manner specified by the culture associated with the current thread.</span></span>  
  
### <a name="concat"></a><span data-ttu-id="9a53b-127">Concat</span><span class="sxs-lookup"><span data-stu-id="9a53b-127">Concat</span></span>  
 <span data-ttu-id="9a53b-128">Die **String.Concat**-Methode kann verwendet werden, um ganz einfach aus mindestens zwei vorhandenen Objekten ein neues Zeichenfolgenobjekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9a53b-128">The **String.Concat** method can be used to easily create a new string object from two or more existing objects.</span></span> <span data-ttu-id="9a53b-129">Die Methode bietet eine sprachunabhängige Möglichkeit zum Verketten von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="9a53b-129">It provides a language-independent way to concatenate strings.</span></span> <span data-ttu-id="9a53b-130">Diese Methode akzeptiert alle von **System.Object** abgeleiteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="9a53b-130">This method accepts any class that derives from **System.Object**.</span></span> <span data-ttu-id="9a53b-131">Das folgende Beispiel erstellt eine Zeichenfolge aus zwei vorhandenen Zeichenfolgenobjekten und einem Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="9a53b-131">The following example creates a string from two existing string objects and a separating character.</span></span>  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### <a name="join"></a><span data-ttu-id="9a53b-132">Join</span><span class="sxs-lookup"><span data-stu-id="9a53b-132">Join</span></span>  
 <span data-ttu-id="9a53b-133">Die **String.Join**-Methode erstellt eine neue Zeichenfolge aus einem Array aus Zeichenfolgen und einem Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="9a53b-133">The **String.Join** method creates a new string from an array of strings and a separator string.</span></span> <span data-ttu-id="9a53b-134">Diese Methode ist nützlich, wenn Sie mehrere Zeichenfolgen miteinander verketten möchten. Sie erstellt eine Liste, die z.B. durch ein Komma getrennt sein kann.</span><span class="sxs-lookup"><span data-stu-id="9a53b-134">This method is useful if you want to concatenate multiple strings together, making a list perhaps separated by a comma.</span></span>  
  
 <span data-ttu-id="9a53b-135">Das folgende Beispiel verwendet ein Leerzeichen, um ein Zeichenfolgenarray zu binden.</span><span class="sxs-lookup"><span data-stu-id="9a53b-135">The following example uses a space to bind a string array.</span></span>  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### <a name="insert"></a><span data-ttu-id="9a53b-136">Insert</span><span class="sxs-lookup"><span data-stu-id="9a53b-136">Insert</span></span>  
 <span data-ttu-id="9a53b-137">Die **String.Insert**-Methode erstellt eine neue Zeichenfolge, indem sie eine Zeichenfolge an einer angegebenen Position in einer anderen Zeichenfolge einfügt.</span><span class="sxs-lookup"><span data-stu-id="9a53b-137">The **String.Insert** method creates a new string by inserting a string into a specified position in another string.</span></span> <span data-ttu-id="9a53b-138">Diese Methode verwendet einen nullbasierten Index.</span><span class="sxs-lookup"><span data-stu-id="9a53b-138">This method uses a zero-based index.</span></span> <span data-ttu-id="9a53b-139">Das folgende Beispiel fügt eine Zeichenfolge an der fünften Indexposition von `MyString` ein und erstellt mit diesem Wert eine neue Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9a53b-139">The following example inserts a string into the fifth index position of `MyString` and creates a new string with this value.</span></span>  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### <a name="copyto"></a><span data-ttu-id="9a53b-140">CopyTo</span><span class="sxs-lookup"><span data-stu-id="9a53b-140">CopyTo</span></span>  
 <span data-ttu-id="9a53b-141">Die **String.CopyTo**-Methode kopiert Teile einer Zeichenfolge in ein Zeichenarray.</span><span class="sxs-lookup"><span data-stu-id="9a53b-141">The **String.CopyTo** method copies portions of a string into an array of characters.</span></span> <span data-ttu-id="9a53b-142">Sie können sowohl den Startindex der Zeichenfolge als auch die Anzahl der zu kopierenden Zeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="9a53b-142">You can specify both the beginning index of the string and the number of characters to be copied.</span></span> <span data-ttu-id="9a53b-143">Diese Methode akzeptiert den Quellindex, ein Array aus Zeichen, den Zielindex und die Anzahl der zu kopierenden Zeichen.</span><span class="sxs-lookup"><span data-stu-id="9a53b-143">This method takes the source index, an array of characters, the destination index, and the number of characters to copy.</span></span> <span data-ttu-id="9a53b-144">Alle Indizes sind nullbasiert.</span><span class="sxs-lookup"><span data-stu-id="9a53b-144">All indexes are zero-based.</span></span>  
  
 <span data-ttu-id="9a53b-145">Das folgende Beispiel verwendet die **CopyTo**-Methode, um die Zeichen des Worts „Hello“ aus einem Zeichenfolgenobjekt in die erste Indexposition eines Zeichenarrays zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="9a53b-145">The following example uses the **CopyTo** method to copy the characters of the word "Hello" from a string object to the first index position of an array of characters.</span></span>  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="9a53b-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a53b-146">See also</span></span>

- [<span data-ttu-id="9a53b-147">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="9a53b-147">Basic String Operations</span></span>](basic-string-operations.md)
- [<span data-ttu-id="9a53b-148">Kombinierte Formatierung</span><span class="sxs-lookup"><span data-stu-id="9a53b-148">Composite Formatting</span></span>](composite-formatting.md)
