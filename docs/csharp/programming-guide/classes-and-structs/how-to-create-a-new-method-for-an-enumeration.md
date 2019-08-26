---
title: 'Vorgehensweise: Erstellen einer neuen Methode für eine Enumeration – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 99a2005e1a64fa214776145a903341fb162f0633
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69597042"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a><span data-ttu-id="383c0-102">Vorgehensweise: Erstellen einer neuen Methode für eine Enumeration (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="383c0-102">How to: Create a New Method for an Enumeration (C# Programming Guide)</span></span>
<span data-ttu-id="383c0-103">Sie können Erweiterungsmethoden verwenden, um für einen bestimmten Enumerationstyp spezifische Funktionen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="383c0-103">You can use extension methods to add functionality specific to a particular enum type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="383c0-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="383c0-104">Example</span></span>  
 <span data-ttu-id="383c0-105">Im folgenden Beispiel stellt die `Grades`-Enumeration die möglichen Noten in Buchstaben dar, die ein Schüler im Unterricht erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="383c0-105">In the following example, the `Grades` enumeration represents the possible letter grades that a student may receive in a class.</span></span> <span data-ttu-id="383c0-106">Eine Erweiterungsmethode mit dem Namen `Passing` wird dem `Grades`-Typ hinzugefügt, sodass jede Instanz dieses Typs nun „weiß“, ob sie eine Note darstellt, mit der der Schüler bestanden hat.</span><span class="sxs-lookup"><span data-stu-id="383c0-106">An extension method named `Passing` is added to the `Grades` type so that each instance of that type now "knows" whether it represents a passing grade or not.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#2)]  
  
 <span data-ttu-id="383c0-107">Beachten Sie, dass die `Extensions`-Klasse auch eine statische Variable enthält, die dynamisch aktualisiert wird, und dass der Rückgabewert der Erweiterungsmethode den aktuellen Wert der Variablen darstellt.</span><span class="sxs-lookup"><span data-stu-id="383c0-107">Note that the `Extensions` class also contains a static variable that is updated dynamically and that the return value of the extension method reflects the current value of that variable.</span></span> <span data-ttu-id="383c0-108">Dies zeigt, dass hinter den Kulissen Erweiterungsmethoden direkt auf der statischen Klasse aufgerufen werden, in der sie definiert sind.</span><span class="sxs-lookup"><span data-stu-id="383c0-108">This demonstrates that, behind the scenes, extension methods are invoked directly on the static class in which they are defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="383c0-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="383c0-109">See also</span></span>

- [<span data-ttu-id="383c0-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="383c0-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="383c0-111">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="383c0-111">Extension Methods</span></span>](./extension-methods.md)
