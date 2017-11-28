---
title: "Gewusst wie: Erstellen einer neuen Methode für eine Enumeration (C#-Programmierhandbuch)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
caps.latest.revision: "7"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3cc15d24c9ba954a19fb87d4e364ac6e7f78e8b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a><span data-ttu-id="3a8e7-102">Gewusst wie: Erstellen einer neuen Methode für eine Enumeration (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="3a8e7-102">How to: Create a New Method for an Enumeration (C# Programming Guide)</span></span>
<span data-ttu-id="3a8e7-103">Sie können Erweiterungsmethoden verwenden, um für einen bestimmten Enumerationstyp spezifische Funktionen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3a8e7-103">You can use extension methods to add functionality specific to a particular enum type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a8e7-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3a8e7-104">Example</span></span>  
 <span data-ttu-id="3a8e7-105">Im folgenden Beispiel stellt die `Grades`-Enumeration die möglichen Noten in Buchstaben dar, die ein Schüler im Unterricht erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="3a8e7-105">In the following example, the `Grades` enumeration represents the possible letter grades that a student may receive in a class.</span></span> <span data-ttu-id="3a8e7-106">Eine Erweiterungsmethode mit dem Namen `Passing` wird dem `Grades`-Typ hinzugefügt, sodass jede Instanz dieses Typs nun „weiß“, ob sie eine Note darstellt, mit der der Schüler bestanden hat.</span><span class="sxs-lookup"><span data-stu-id="3a8e7-106">An extension method named `Passing` is added to the `Grades` type so that each instance of that type now "knows" whether it represents a passing grade or not.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-create-a-new-method-for-an-enumeration_1.cs)]  
  
 <span data-ttu-id="3a8e7-107">Beachten Sie, dass die `Extensions`-Klasse auch eine statische Variable enthält, die dynamisch aktualisiert wird, und dass der Rückgabewert der Erweiterungsmethode den aktuellen Wert der Variablen darstellt.</span><span class="sxs-lookup"><span data-stu-id="3a8e7-107">Note that the `Extensions` class also contains a static variable that is updated dynamically and that the return value of the extension method reflects the current value of that variable.</span></span> <span data-ttu-id="3a8e7-108">Dies zeigt, dass hinter den Kulissen Erweiterungsmethoden direkt auf der statischen Klasse aufgerufen werden, in der sie definiert sind.</span><span class="sxs-lookup"><span data-stu-id="3a8e7-108">This demonstrates that, behind the scenes, extension methods are invoked directly on the static class in which they are defined.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3a8e7-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="3a8e7-109">Compiling the Code</span></span>  
 <span data-ttu-id="3a8e7-110">Um diesen Code auszuführen, kopieren Sie ihn, und fügen Sie ihn in ein Visual C#-Konsolenanwendungsprojekt ein, das in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)] erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="3a8e7-110">To run this code, copy and paste it into a Visual C# console application project that has been created in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="3a8e7-111">Standardmäßig wird dieses Projekt mit Version 3.5 von [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verwendet und verfügt über einen Verweis auf „System.Core.dll“ und eine `using`-Anweisung für „System.Linq“.</span><span class="sxs-lookup"><span data-stu-id="3a8e7-111">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a `using` directive for System.Linq.</span></span> <span data-ttu-id="3a8e7-112">Wenn eine oder mehrere dieser Anforderungen im Projekt nicht vorhanden sind, können Sie sie manuell hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3a8e7-112">If one or more of these requirements are missing from the project, you can add them manually.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a8e7-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a8e7-113">See Also</span></span>  
 [<span data-ttu-id="3a8e7-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3a8e7-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3a8e7-115">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="3a8e7-115">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
