---
title: Arbeiten mit dynamischen Objekten (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d1e1c4f7338daad0f1101f6e886eba6c37316b0e
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="working-with-dynamic-objects-visual-basic"></a><span data-ttu-id="486d8-102">Arbeiten mit dynamischen Objekten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="486d8-102">Working with Dynamic Objects (Visual Basic)</span></span>
<span data-ttu-id="486d8-103">Dynamische Objekte bieten eine weitere Möglichkeit, außer der `Object` Typ späte Bindung an ein Objekt zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="486d8-103">Dynamic objects provide another way, other than the `Object` type, to late bind to an object at run time.</span></span> <span data-ttu-id="486d8-104">Ein dynamisches Objekt macht Member wie Eigenschaften und Methoden zur Laufzeit mithilfe von dynamischen Schnittstellen, die in definiert sind die <xref:System.Dynamic>Namespace.</xref:System.Dynamic></span><span class="sxs-lookup"><span data-stu-id="486d8-104">A dynamic object exposes members such as properties and methods at run time by using dynamic interfaces that are defined in the <xref:System.Dynamic> namespace.</span></span> <span data-ttu-id="486d8-105">Sie können die Klassen in der <xref:System.Dynamic>Namespace zum Erstellen von Objekten, die mit Datenstrukturen, die nicht statischen Typ oder Format entsprechen.</xref:System.Dynamic></span><span class="sxs-lookup"><span data-stu-id="486d8-105">You can use the classes in the <xref:System.Dynamic> namespace to create objects that work with data structures that do not match a static type or format.</span></span> <span data-ttu-id="486d8-106">Sie können auch die dynamische Objekte, die in dynamischen Sprachen wie IronPython und IronRuby definiert sind.</span><span class="sxs-lookup"><span data-stu-id="486d8-106">You can also use the dynamic objects that are defined in dynamic languages such as IronPython and IronRuby.</span></span> <span data-ttu-id="486d8-107">Beispiele, die zeigen, wie dynamische Objekte erstellt, oder verwenden Sie ein dynamisches Objekt in einer dynamischen Sprache definiert werden, finden Sie unter [Exemplarische Vorgehensweise: Erstellen und verwenden dynamische Objekte](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, oder <xref:System.Dynamic.ExpandoObject>.</xref:System.Dynamic.ExpandoObject> </xref:System.Dynamic.DynamicObject></span><span class="sxs-lookup"><span data-stu-id="486d8-107">For examples that show how to create dynamic objects or use a dynamic object defined in a dynamic language, see [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, or <xref:System.Dynamic.ExpandoObject>.</span></span>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="486d8-108">Mithilfe von Objekten aus der dynamic Language Runtime und dynamische Sprachen wie IronPython und IronRuby gebunden die <xref:System.Dynamic.IDynamicMetaObjectProvider>Schnittstelle.</xref:System.Dynamic.IDynamicMetaObjectProvider></span><span class="sxs-lookup"><span data-stu-id="486d8-108"> binds to objects from the dynamic language runtime and dynamic languages such as IronPython and IronRuby by using the <xref:System.Dynamic.IDynamicMetaObjectProvider> interface.</span></span> <span data-ttu-id="486d8-109">Beispiele für Klassen, implementieren die `IDynamicMetaObjectProvider` Schnittstelle sind die <xref:System.Dynamic.DynamicObject>und <xref:System.Dynamic.ExpandoObject>Klassen.</xref:System.Dynamic.ExpandoObject> </xref:System.Dynamic.DynamicObject></span><span class="sxs-lookup"><span data-stu-id="486d8-109">Examples of classes that implement the `IDynamicMetaObjectProvider` interface are the <xref:System.Dynamic.DynamicObject> and <xref:System.Dynamic.ExpandoObject> classes.</span></span>  
  
 <span data-ttu-id="486d8-110">Bei ein spät gebundenen Aufruf an ein Objekt implementiert die `IDynamicMetaObjectProvider` -Schnittstelle [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] mithilfe dieser Schnittstelle von dynamischen Objekts gebunden.</span><span class="sxs-lookup"><span data-stu-id="486d8-110">If a late-bound call is made to an object that implements the `IDynamicMetaObjectProvider` interface, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] binds to the dynamic object by using that interface.</span></span> <span data-ttu-id="486d8-111">Erfolgt ein spät gebundenen Aufruf auf ein Objekt, das nicht implementiert die `IDynamicMetaObjectProvider` -Schnittstelle, oder, wenn der Aufruf von der `IDynamicMetaObjectProvider` -Schnittstelle ein Fehler auftritt, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] bindet an das Objekt mithilfe der Funktionen für späte Bindung von der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="486d8-111">If a late-bound call is made to an object that does not implement the `IDynamicMetaObjectProvider` interface, or if the call to the `IDynamicMetaObjectProvider` interface fails, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] binds to the object by using the late-binding capabilities of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="486d8-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="486d8-112">See Also</span></span>  
 <span data-ttu-id="486d8-113"><xref:System.Dynamic.DynamicObject></xref:System.Dynamic.DynamicObject></span><span class="sxs-lookup"><span data-stu-id="486d8-113"><xref:System.Dynamic.DynamicObject></span></span>   
 <span data-ttu-id="486d8-114"><xref:System.Dynamic.ExpandoObject></xref:System.Dynamic.ExpandoObject></span><span class="sxs-lookup"><span data-stu-id="486d8-114"><xref:System.Dynamic.ExpandoObject></span></span>   
<span data-ttu-id="486d8-115"> [Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md) </span><span class="sxs-lookup"><span data-stu-id="486d8-115"> [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md) </span></span>  
<span data-ttu-id="486d8-116"> [Frühes und spätes Binden](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)</span><span class="sxs-lookup"><span data-stu-id="486d8-116"> [Early and Late Binding](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)</span></span>
