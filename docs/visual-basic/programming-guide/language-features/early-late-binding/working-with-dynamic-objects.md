---
title: "Arbeiten mit dynamischen Objekten (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: da70c1e4c7398ad46d48c85b62ab884675bd1a73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="working-with-dynamic-objects-visual-basic"></a><span data-ttu-id="219de-102">Arbeiten mit dynamischen Objekten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="219de-102">Working with Dynamic Objects (Visual Basic)</span></span>
<span data-ttu-id="219de-103">Dynamische Objekte bieten eine weitere Möglichkeit, andere als die `Object` Typ späte Bindung an ein Objekt zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="219de-103">Dynamic objects provide another way, other than the `Object` type, to late bind to an object at run time.</span></span> <span data-ttu-id="219de-104">Ein dynamisches Objekt macht Elemente wie z. B. Eigenschaften und Methoden zur Laufzeit mithilfe von dynamischen Schnittstellen, die in definierten der <xref:System.Dynamic> Namespace.</span><span class="sxs-lookup"><span data-stu-id="219de-104">A dynamic object exposes members such as properties and methods at run time by using dynamic interfaces that are defined in the <xref:System.Dynamic> namespace.</span></span> <span data-ttu-id="219de-105">Sie können die Klassen in der <xref:System.Dynamic> Namespace zum Erstellen von Objekten, die mit Datenstrukturen zu arbeiten, der nicht statischen Typ oder Format übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="219de-105">You can use the classes in the <xref:System.Dynamic> namespace to create objects that work with data structures that do not match a static type or format.</span></span> <span data-ttu-id="219de-106">Sie können auch die dynamische Objekte, die in dynamischen Sprachen wie z. B. IronPython und IronRuby definiert sind.</span><span class="sxs-lookup"><span data-stu-id="219de-106">You can also use the dynamic objects that are defined in dynamic languages such as IronPython and IronRuby.</span></span> <span data-ttu-id="219de-107">Finden Sie Beispiele, die zeigen, wie Sie dynamische Objekte erstellen, oder verwenden Sie ein dynamisches Objekt in einer dynamischen Sprache definiert, [Exemplarische Vorgehensweise: Erstellen und mit dynamischen Objekten](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, oder <xref:System.Dynamic.ExpandoObject>.</span><span class="sxs-lookup"><span data-stu-id="219de-107">For examples that show how to create dynamic objects or use a dynamic object defined in a dynamic language, see [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, or <xref:System.Dynamic.ExpandoObject>.</span></span>  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="219de-108">bindet auf Objekte aus der dynamic Language Runtime und dynamischen Sprachen wie z. B. IronPython und IronRuby mithilfe der <xref:System.Dynamic.IDynamicMetaObjectProvider> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="219de-108"> binds to objects from the dynamic language runtime and dynamic languages such as IronPython and IronRuby by using the <xref:System.Dynamic.IDynamicMetaObjectProvider> interface.</span></span> <span data-ttu-id="219de-109">Beispiele für Klassen, implementieren die `IDynamicMetaObjectProvider` Schnittstelle werden die <xref:System.Dynamic.DynamicObject> und <xref:System.Dynamic.ExpandoObject> Klassen.</span><span class="sxs-lookup"><span data-stu-id="219de-109">Examples of classes that implement the `IDynamicMetaObjectProvider` interface are the <xref:System.Dynamic.DynamicObject> and <xref:System.Dynamic.ExpandoObject> classes.</span></span>  
  
 <span data-ttu-id="219de-110">Wenn Sie einen spät gebundenen Aufruf zu einem Objekt ausgeführt wird, die implementiert die `IDynamicMetaObjectProvider` Schnittstelle [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] mithilfe dieser Schnittstelle von dynamischen Objekts gebunden.</span><span class="sxs-lookup"><span data-stu-id="219de-110">If a late-bound call is made to an object that implements the `IDynamicMetaObjectProvider` interface, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] binds to the dynamic object by using that interface.</span></span> <span data-ttu-id="219de-111">Wenn Sie einen spät gebundenen Aufruf zu einem Objekt ausgeführt wird, die nicht implementiert die `IDynamicMetaObjectProvider` -Schnittstelle, oder, wenn der Aufruf von der `IDynamicMetaObjectProvider` -Schnittstelle ein Fehler auftritt, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] bindet das Objekt mithilfe der Funktionen spätes Binden, der die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="219de-111">If a late-bound call is made to an object that does not implement the `IDynamicMetaObjectProvider` interface, or if the call to the `IDynamicMetaObjectProvider` interface fails, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] binds to the object by using the late-binding capabilities of the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="219de-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="219de-112">See Also</span></span>  
 <xref:System.Dynamic.DynamicObject>  
 <xref:System.Dynamic.ExpandoObject>  
 [<span data-ttu-id="219de-113">Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten</span><span class="sxs-lookup"><span data-stu-id="219de-113">Walkthrough: Creating and Using Dynamic Objects</span></span>](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)  
 [<span data-ttu-id="219de-114">Frühes und spätes Binden</span><span class="sxs-lookup"><span data-stu-id="219de-114">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
