---
title: 'Gewusst wie: Initialisieren eines Wörterbuchs mit einem Auflistungsinitialisierer (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
caps.latest.revision: ''
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8b8de5fb85a839d52ad00ad552ef823d9817e9b7
ms.sourcegitcommit: 32172ca05d5dcce7ef3d327b9c8639c736e0fe2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2018
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a><span data-ttu-id="97f4b-102">Gewusst wie: Initialisieren eines Wörterbuchs mit einem Auflistungsinitialisierer (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="97f4b-102">How to: Initialize a Dictionary with a Collection Initializer (C# Programming Guide)</span></span>
<span data-ttu-id="97f4b-103">Eine <xref:System.Collections.Generic.Dictionary`2> enthält eine Sammlung von Schlüssel-Wert-Paaren.</span><span class="sxs-lookup"><span data-stu-id="97f4b-103">A <xref:System.Collections.Generic.Dictionary`2> contains a collection of key/value pairs.</span></span> <span data-ttu-id="97f4b-104">Die <xref:System.Collections.Generic.Dictionary`2.Add*>-Methode nimmt zwei Parameter an, einen für den Schlüssel und einen für den Wert.</span><span class="sxs-lookup"><span data-stu-id="97f4b-104">Its <xref:System.Collections.Generic.Dictionary`2.Add*> method takes two parameters, one for the key and one for the value.</span></span> <span data-ttu-id="97f4b-105">Um eine <xref:System.Collections.Generic.Dictionary`2>-Klasse oder eine beliebige Sammlung zu initialisieren, deren `Add`-Methode mehrere Parameter annimmt, schließen Sie einen Satz von Parametern in Klammern ein, so wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="97f4b-105">To initialize a <xref:System.Collections.Generic.Dictionary`2>, or any collection whose `Add` method takes multiple parameters, enclose each set of parameters in braces as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97f4b-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97f4b-106">Example</span></span>  
 <span data-ttu-id="97f4b-107">Im folgenden Codebeispiel wird <xref:System.Collections.Generic.Dictionary`2> mit Instanzen vom Typ `StudentName` initialisiert.</span><span class="sxs-lookup"><span data-stu-id="97f4b-107">In the following code example, a <xref:System.Collections.Generic.Dictionary`2> is initialized with instances of type `StudentName`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]  
  
 <span data-ttu-id="97f4b-108">Beachten Sie die zwei Paare geschweifter Klammern in jedem Element der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="97f4b-108">Note the two pairs of braces in each element of the collection.</span></span> <span data-ttu-id="97f4b-109">Die inneren Klammern umschließen den Objektinitialisierer für `StudentName`, und die äußeren Klammern umschließen den Initialisierer für das Schlüssel/Wertpaar, das `students`<xref:System.Collections.Generic.Dictionary`2> hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="97f4b-109">The innermost braces enclose the object initializer for the `StudentName`, and the outermost braces enclose the initializer for the key/value pair that will be added to the `students`<xref:System.Collections.Generic.Dictionary`2>.</span></span> <span data-ttu-id="97f4b-110">Schließlich wird der ganze Auflistungsinitialisierer für das Wörterbuch in geschweifte Klammern eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="97f4b-110">Finally, the whole collection initializer for the dictionary is enclosed in braces.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="97f4b-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="97f4b-111">Compiling the Code</span></span>  
 <span data-ttu-id="97f4b-112">Um diesen Code auszuführen, kopieren Sie die Klasse, und fügen Sie sie in ein Visual C#-Konsolenanwendungsprojekt ein, das in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)] erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="97f4b-112">To run this code, copy and paste the class into a Visual C# console application project that has been created in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="97f4b-113">Standardmäßig wird dieses Projekt mit Version 3.5 von [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verwendet und verfügt über einen Verweis auf „System.Core.dll“ und eine using-Anweisung für „System.Linq“.</span><span class="sxs-lookup"><span data-stu-id="97f4b-113">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a using directive for System.Linq.</span></span> <span data-ttu-id="97f4b-114">Wenn eine oder mehrere dieser Anforderungen im Projekt nicht vorhanden sind, können Sie sie manuell hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="97f4b-114">If one or more of these requirements are missing from the project, you can add them manually.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97f4b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97f4b-115">See Also</span></span>  
 [<span data-ttu-id="97f4b-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="97f4b-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="97f4b-117">Objekt- und Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="97f4b-117">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
