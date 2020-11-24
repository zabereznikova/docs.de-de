---
title: 'Gewusst wie: Erstellen einer neuen Methode für eine Enumeration – C#-Programmierhandbuch'
description: Informationen zur Verwendung von Erweiterungsmethoden zum Hinzuzufügen von Funktionen zu einer Enumeration in C# Dieses Beispiel zeigt eine Erweiterungsmethode mit dem Namen „Passing“ für eine Aufzählung namens „Grades“.
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 862eb86a5b0cc6b95302260874222bbc09d98132
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099411"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a><span data-ttu-id="9b2ce-104">Gewusst wie: Erstellen einer neuen Methode für eine Enumeration (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="9b2ce-104">How to create a new method for an enumeration (C# Programming Guide)</span></span>

<span data-ttu-id="9b2ce-105">Sie können Erweiterungsmethoden verwenden, um für einen bestimmten Enumerationstyp spezifische Funktionen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9b2ce-105">You can use extension methods to add functionality specific to a particular enum type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b2ce-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b2ce-106">Example</span></span>  

 <span data-ttu-id="9b2ce-107">Im folgenden Beispiel stellt die `Grades`-Enumeration die möglichen Noten in Buchstaben dar, die ein Schüler im Unterricht erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="9b2ce-107">In the following example, the `Grades` enumeration represents the possible letter grades that a student may receive in a class.</span></span> <span data-ttu-id="9b2ce-108">Eine Erweiterungsmethode mit dem Namen `Passing` wird dem `Grades`-Typ hinzugefügt, sodass jede Instanz dieses Typs nun „weiß“, ob sie eine Note darstellt, mit der der Schüler bestanden hat.</span><span class="sxs-lookup"><span data-stu-id="9b2ce-108">An extension method named `Passing` is added to the `Grades` type so that each instance of that type now "knows" whether it represents a passing grade or not.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#2)]  
  
 <span data-ttu-id="9b2ce-109">Beachten Sie, dass die `Extensions`-Klasse auch eine statische Variable enthält, die dynamisch aktualisiert wird, und dass der Rückgabewert der Erweiterungsmethode den aktuellen Wert der Variablen darstellt.</span><span class="sxs-lookup"><span data-stu-id="9b2ce-109">Note that the `Extensions` class also contains a static variable that is updated dynamically and that the return value of the extension method reflects the current value of that variable.</span></span> <span data-ttu-id="9b2ce-110">Dies zeigt, dass hinter den Kulissen Erweiterungsmethoden direkt auf der statischen Klasse aufgerufen werden, in der sie definiert sind.</span><span class="sxs-lookup"><span data-stu-id="9b2ce-110">This demonstrates that, behind the scenes, extension methods are invoked directly on the static class in which they are defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b2ce-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b2ce-111">See also</span></span>

- [<span data-ttu-id="9b2ce-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9b2ce-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9b2ce-113">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="9b2ce-113">Extension Methods</span></span>](./extension-methods.md)
