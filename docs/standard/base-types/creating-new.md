---
title: Erstellen neuer Zeichenfolgen in .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d000cd88fc9ee9fd48ef25e9bb4982688564a2a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="creating-new-strings-in-net"></a><span data-ttu-id="2487f-102">Erstellen neuer Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="2487f-102">Creating New Strings in .NET</span></span>
<span data-ttu-id="2487f-103">Die [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] können Zeichenfolgen, die mit einfachen Zuordnung erstellt werden, und überlädt auch einen Klassenkonstruktor zum Erstellen von Zeichenfolgen mit einer Reihe von unterschiedlichen Parametern zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="2487f-103">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] allows strings to be created using simple assignment, and also overloads a class constructor to support string creation using a number of different parameters.</span></span> <span data-ttu-id="2487f-104">Die [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] auch stellt mehrere Methoden in der <xref:System.String?displayProperty=nameWithType> -Klasse, die neue Zeichenfolge erstellt Objekte nach Kombination von mehreren Zeichenfolgen, Arrays von Zeichenfolgen oder Objekte.</span><span class="sxs-lookup"><span data-stu-id="2487f-104">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] also provides several methods in the <xref:System.String?displayProperty=nameWithType> class that create new string objects by combining several strings, arrays of strings, or objects.</span></span>  
  
## <a name="creating-strings-using-assignment"></a><span data-ttu-id="2487f-105">Erstellen von Zeichenfolgen mithilfe von Zuweisung</span><span class="sxs-lookup"><span data-stu-id="2487f-105">Creating Strings Using Assignment</span></span>  
 <span data-ttu-id="2487f-106">Die einfachste Möglichkeit zum Erstellen eines neuen <xref:System.String> Objekt besteht darin, ein Zeichenfolgenliteral in weisen eine <xref:System.String> Objekt.</span><span class="sxs-lookup"><span data-stu-id="2487f-106">The easiest way to create a new <xref:System.String> object is simply to assign a string literal to a <xref:System.String> object.</span></span>  
  
## <a name="creating-strings-using-a-class-constructor"></a><span data-ttu-id="2487f-107">Erstellen von Zeichenfolgen mithilfe eines Klassenkonstruktors</span><span class="sxs-lookup"><span data-stu-id="2487f-107">Creating Strings Using a Class Constructor</span></span>  
 <span data-ttu-id="2487f-108">Können Sie Überladungen von der <xref:System.String> Klassenkonstruktor Zeichenfolgen aus Zeichenarrays zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2487f-108">You can use overloads of the <xref:System.String> class constructor to create strings from character arrays.</span></span> <span data-ttu-id="2487f-109">Sie können auch eine neue Zeichenfolge erstellen, indem Sie ein bestimmtes Zeichen eine angegebene Anzahl von Malen duplizieren.</span><span class="sxs-lookup"><span data-stu-id="2487f-109">You can also create a new string by duplicating a particular character a specified number of times.</span></span>  
  
## <a name="methods-that-return-strings"></a><span data-ttu-id="2487f-110">Methoden, die Zeichenfolgen zurückgeben</span><span class="sxs-lookup"><span data-stu-id="2487f-110">Methods that Return Strings</span></span>  
 <span data-ttu-id="2487f-111">Die folgende Tabelle führt verschiedene nützliche Methoden auf, die neue Zeichenfolgenobjekte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="2487f-111">The following table lists several useful methods that return new string objects.</span></span>  
  
|<span data-ttu-id="2487f-112">Methodenname</span><span class="sxs-lookup"><span data-stu-id="2487f-112">Method name</span></span>|<span data-ttu-id="2487f-113">Verwendung</span><span class="sxs-lookup"><span data-stu-id="2487f-113">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|<span data-ttu-id="2487f-114">Erstellt eine formatierte Zeichenfolge aus einem Satz von Eingabeobjekten.</span><span class="sxs-lookup"><span data-stu-id="2487f-114">Builds a formatted string from a set of input objects.</span></span>|  
|<xref:System.String.Concat%2A?displayProperty=nameWithType>|<span data-ttu-id="2487f-115">Erstellt Zeichenfolgen aus mindestens zwei Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="2487f-115">Builds strings from two or more strings.</span></span>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|<span data-ttu-id="2487f-116">Erstellt eine neue Zeichenfolge durch Kombinieren eines Arrays aus Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="2487f-116">Builds a new string by combining an array of strings.</span></span>|  
|<xref:System.String.Insert%2A?displayProperty=nameWithType>|<span data-ttu-id="2487f-117">Erstellt eine neue Zeichenfolge durch Einfügen einer Zeichenfolge in den angegebenen Index einer vorhandenen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2487f-117">Builds a new string by inserting a string into the specified index of an existing string.</span></span>|  
|<xref:System.String.CopyTo%2A?displayProperty=nameWithType>|<span data-ttu-id="2487f-118">Kopiert angegebene Zeichen in einer Zeichenfolge in eine bestimmte Position in einem Array aus Zeichen.</span><span class="sxs-lookup"><span data-stu-id="2487f-118">Copies specified characters in a string into a specified position in an array of characters.</span></span>|  
  
### <a name="format"></a><span data-ttu-id="2487f-119">Format</span><span class="sxs-lookup"><span data-stu-id="2487f-119">Format</span></span>  
 <span data-ttu-id="2487f-120">Sie können die **String.Format** -Methode formatierte Zeichenfolgen erstellen und Verketten von Zeichenfolgen, die mehrere Objekte darstellt.</span><span class="sxs-lookup"><span data-stu-id="2487f-120">You can use the **String.Format** method to create formatted strings and concatenate strings representing multiple objects.</span></span> <span data-ttu-id="2487f-121">Diese Methode konvertiert automatisch alle übergebenen Objekte in eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2487f-121">This method automatically converts any passed object into a string.</span></span> <span data-ttu-id="2487f-122">Z. B., wenn die Anwendung angezeigt, muss eine **Int32** Wert und eine **"DateTime"** Wert für den Benutzer können Sie problemlos eine Zeichenfolge, um diese Werte über darstellen erstellen die **Format**Methode.</span><span class="sxs-lookup"><span data-stu-id="2487f-122">For example, if your application must display an **Int32** value and a **DateTime** value to the user, you can easily construct a string to represent these values using the **Format** method.</span></span> <span data-ttu-id="2487f-123">Informationen zu den mit dieser Methode verwendeten Formatierungskonventionen finden Sie im Abschnitt [Zusammengesetzte Formatierung](../../../docs/standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="2487f-123">For information about formatting conventions used with this method, see the section on [composite formatting](../../../docs/standard/base-types/composite-formatting.md).</span></span>  
  
 <span data-ttu-id="2487f-124">Im folgenden Beispiel wird die **Format** Methode, um eine Zeichenfolge zu erstellen, der eine ganzzahlige Variable verwendet.</span><span class="sxs-lookup"><span data-stu-id="2487f-124">The following example uses the **Format** method to create a string that uses an integer variable.</span></span>  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 <span data-ttu-id="2487f-125">In diesem Beispiel<xref:System.DateTime.Now%2A?displayProperty=nameWithType> zeigt das aktuelle Datum und die Uhrzeit in einer Weise angegeben, die von der Kultur, die dem aktuellen Thread zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2487f-125">In this example,<xref:System.DateTime.Now%2A?displayProperty=nameWithType> displays the current date and time in a manner specified by the culture associated with the current thread.</span></span>  
  
### <a name="concat"></a><span data-ttu-id="2487f-126">Concat</span><span class="sxs-lookup"><span data-stu-id="2487f-126">Concat</span></span>  
 <span data-ttu-id="2487f-127">Die **String.Concat** Methode kann verwendet werden, um ein neues Zeichenfolgeobjekt problemlos aus zwei oder mehr vorhandene Objekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2487f-127">The **String.Concat** method can be used to easily create a new string object from two or more existing objects.</span></span> <span data-ttu-id="2487f-128">Die Methode bietet eine sprachunabhängige Möglichkeit zum Verketten von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="2487f-128">It provides a language-independent way to concatenate strings.</span></span> <span data-ttu-id="2487f-129">Diese Methode akzeptiert jede Klasse, die abgeleitet **System.Object**.</span><span class="sxs-lookup"><span data-stu-id="2487f-129">This method accepts any class that derives from **System.Object**.</span></span> <span data-ttu-id="2487f-130">Das folgende Beispiel erstellt eine Zeichenfolge aus zwei vorhandenen Zeichenfolgenobjekten und einem Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="2487f-130">The following example creates a string from two existing string objects and a separating character.</span></span>  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### <a name="join"></a><span data-ttu-id="2487f-131">Join</span><span class="sxs-lookup"><span data-stu-id="2487f-131">Join</span></span>  
 <span data-ttu-id="2487f-132">Die **String.Join** Methode erstellt eine neue Zeichenfolge aus einem Array von Zeichenfolgen und ein Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="2487f-132">The **String.Join** method creates a new string from an array of strings and a separator string.</span></span> <span data-ttu-id="2487f-133">Diese Methode ist nützlich, wenn Sie mehrere Zeichenfolgen miteinander verketten möchten. Sie erstellt eine Liste, die z.B. durch ein Komma getrennt sein kann.</span><span class="sxs-lookup"><span data-stu-id="2487f-133">This method is useful if you want to concatenate multiple strings together, making a list perhaps separated by a comma.</span></span>  
  
 <span data-ttu-id="2487f-134">Das folgende Beispiel verwendet ein Leerzeichen, um ein Zeichenfolgenarray zu binden.</span><span class="sxs-lookup"><span data-stu-id="2487f-134">The following example uses a space to bind a string array.</span></span>  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### <a name="insert"></a><span data-ttu-id="2487f-135">Insert</span><span class="sxs-lookup"><span data-stu-id="2487f-135">Insert</span></span>  
 <span data-ttu-id="2487f-136">Die **String.Insert** Methode erstellt eine neue Zeichenfolge, indem eine Zeichenfolge in einer angegebenen Position in einer anderen Zeichenfolge eingefügt.</span><span class="sxs-lookup"><span data-stu-id="2487f-136">The **String.Insert** method creates a new string by inserting a string into a specified position in another string.</span></span> <span data-ttu-id="2487f-137">Diese Methode verwendet einen nullbasierten Index.</span><span class="sxs-lookup"><span data-stu-id="2487f-137">This method uses a zero-based index.</span></span> <span data-ttu-id="2487f-138">Das folgende Beispiel fügt eine Zeichenfolge an der fünften Indexposition von `MyString` ein und erstellt mit diesem Wert eine neue Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2487f-138">The following example inserts a string into the fifth index position of `MyString` and creates a new string with this value.</span></span>  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### <a name="copyto"></a><span data-ttu-id="2487f-139">CopyTo</span><span class="sxs-lookup"><span data-stu-id="2487f-139">CopyTo</span></span>  
 <span data-ttu-id="2487f-140">Die **String.CopyTo** Methode kopiert die Teile einer Zeichenfolge in ein Array von Zeichen.</span><span class="sxs-lookup"><span data-stu-id="2487f-140">The **String.CopyTo** method copies portions of a string into an array of characters.</span></span> <span data-ttu-id="2487f-141">Sie können sowohl den Startindex der Zeichenfolge als auch die Anzahl der zu kopierenden Zeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="2487f-141">You can specify both the beginning index of the string and the number of characters to be copied.</span></span> <span data-ttu-id="2487f-142">Diese Methode akzeptiert den Quellindex, ein Array aus Zeichen, den Zielindex und die Anzahl der zu kopierenden Zeichen.</span><span class="sxs-lookup"><span data-stu-id="2487f-142">This method takes the source index, an array of characters, the destination index, and the number of characters to copy.</span></span> <span data-ttu-id="2487f-143">Alle Indizes sind nullbasiert.</span><span class="sxs-lookup"><span data-stu-id="2487f-143">All indexes are zero-based.</span></span>  
  
 <span data-ttu-id="2487f-144">Im folgenden Beispiel wird die **CopyTo** Methode, um die Zeichen des Worts "Hello" aus einer Zeichenfolge Objekt kopieren, an die erste Indexposition eines Arrays von Zeichen.</span><span class="sxs-lookup"><span data-stu-id="2487f-144">The following example uses the **CopyTo** method to copy the characters of the word "Hello" from a string object to the first index position of an array of characters.</span></span>  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="2487f-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2487f-145">See Also</span></span>  
 [<span data-ttu-id="2487f-146">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="2487f-146">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)  
 [<span data-ttu-id="2487f-147">Kombinierte Formatierung</span><span class="sxs-lookup"><span data-stu-id="2487f-147">Composite Formatting</span></span>](../../../docs/standard/base-types/composite-formatting.md)
