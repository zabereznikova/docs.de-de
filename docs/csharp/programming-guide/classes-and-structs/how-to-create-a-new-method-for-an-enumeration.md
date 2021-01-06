---
title: 'Gewusst wie: Erstellen einer neuen Methode für eine Enumeration – C#-Programmierhandbuch'
description: Informationen zur Verwendung von Erweiterungsmethoden zum Hinzuzufügen von Funktionen zu einer Enumeration in C# Dieses Beispiel zeigt eine Erweiterungsmethode mit dem Namen „Passing“ für eine Aufzählung namens „Grades“.
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 88afff854b8136bde837db8effb0e0eb512e1099
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513093"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a><span data-ttu-id="6b58c-104">Gewusst wie: Erstellen einer neuen Methode für eine Enumeration (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="6b58c-104">How to create a new method for an enumeration (C# Programming Guide)</span></span>

<span data-ttu-id="6b58c-105">Sie können Erweiterungsmethoden verwenden, um für einen bestimmten Enumerationstyp spezifische Funktionen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="6b58c-105">You can use extension methods to add functionality specific to a particular enum type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b58c-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b58c-106">Example</span></span>  

 <span data-ttu-id="6b58c-107">Im folgenden Beispiel stellt die `Grades`-Enumeration die möglichen Noten in Buchstaben dar, die ein Schüler im Unterricht erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="6b58c-107">In the following example, the `Grades` enumeration represents the possible letter grades that a student may receive in a class.</span></span> <span data-ttu-id="6b58c-108">Eine Erweiterungsmethode mit dem Namen `Passing` wird dem `Grades`-Typ hinzugefügt, sodass jede Instanz dieses Typs nun „weiß“, ob sie eine Note darstellt, mit der der Schüler bestanden hat.</span><span class="sxs-lookup"><span data-stu-id="6b58c-108">An extension method named `Passing` is added to the `Grades` type so that each instance of that type now "knows" whether it represents a passing grade or not.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#2)]  
  
 <span data-ttu-id="6b58c-109">Beachten Sie, dass die `Extensions`-Klasse auch eine statische Variable enthält, die dynamisch aktualisiert wird, und dass der Rückgabewert der Erweiterungsmethode den aktuellen Wert der Variablen darstellt.</span><span class="sxs-lookup"><span data-stu-id="6b58c-109">Note that the `Extensions` class also contains a static variable that is updated dynamically and that the return value of the extension method reflects the current value of that variable.</span></span> <span data-ttu-id="6b58c-110">Dies zeigt, dass hinter den Kulissen Erweiterungsmethoden direkt auf der statischen Klasse aufgerufen werden, in der sie definiert sind.</span><span class="sxs-lookup"><span data-stu-id="6b58c-110">This demonstrates that, behind the scenes, extension methods are invoked directly on the static class in which they are defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b58c-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b58c-111">See also</span></span>

- [<span data-ttu-id="6b58c-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6b58c-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6b58c-113">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="6b58c-113">Extension Methods</span></span>](./extension-methods.md)
