---
title: Reflektion (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: d991bc0f-d16a-4ac5-9351-70e5c5b9891b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: acfcb519128de0d616757398c94ec70dc7de6ef1
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="reflection-visual-basic"></a><span data-ttu-id="b0a3f-102">Reflektion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b0a3f-102">Reflection (Visual Basic)</span></span>
<span data-ttu-id="b0a3f-103">Reflektion stellt Objekte (des Typs <xref:System.Type>), die Assemblys, Module und Typen beschreiben.</xref:System.Type></span><span class="sxs-lookup"><span data-stu-id="b0a3f-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="b0a3f-104">Sie können mithilfe von Reflektion dynamisch eine Instanz eines Typs erstellen, Typen an ein vorhandenes Objekt binden oder Typinformationen von vorhandenen Objekten und Aufrufen ihrer Methoden oder dessen Felder und Eigenschaften zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b0a3f-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="b0a3f-105">Wenn Sie Attribute in Ihrem Code verwenden, können Sie Reflektion, darauf zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="b0a3f-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="b0a3f-106">Weitere Informationen finden Sie unter [Attribute](https://msdn.microsoft.com/library/5x6cd29c).</span><span class="sxs-lookup"><span data-stu-id="b0a3f-106">For more information, see [Attributes](https://msdn.microsoft.com/library/5x6cd29c).</span></span>  
  
 <span data-ttu-id="b0a3f-107">Hier ist ein einfaches Beispiel veranschaulicht die Verwendung der statischen Methode `GetType` - geerbten alle Typen aus der `Object` -Basisklasse - zum Abrufen des Typs einer Variablen:</span><span class="sxs-lookup"><span data-stu-id="b0a3f-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```vb  
' Using GetType to obtain type information:  
Dim i As Integer = 42  
Dim type As System.Type = i.GetType()  
System.Console.WriteLine(type)  
```  
  
 <span data-ttu-id="b0a3f-108">Die Ausgabe lautet:</span><span class="sxs-lookup"><span data-stu-id="b0a3f-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="b0a3f-109">Das folgende Beispiel verwendet Reflektion, um den vollständigen Namen der geladenen Assembly abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b0a3f-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```vb  
' Using Reflection to get information from an Assembly:  
Dim info As System.Reflection.Assembly = GetType(System.Int32).Assembly  
System.Console.WriteLine(info)  
```  
  
 <span data-ttu-id="b0a3f-110">Die Ausgabe lautet:</span><span class="sxs-lookup"><span data-stu-id="b0a3f-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
## <a name="reflection-overview"></a><span data-ttu-id="b0a3f-111">Übersicht über Reflektion</span><span class="sxs-lookup"><span data-stu-id="b0a3f-111">Reflection Overview</span></span>  
 <span data-ttu-id="b0a3f-112">Reflektion ist in folgenden Situationen nützlich:</span><span class="sxs-lookup"><span data-stu-id="b0a3f-112">Reflection is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="b0a3f-113">Wenn Sie Attribute in den Metadaten des Programms zugreifen müssen.</span><span class="sxs-lookup"><span data-stu-id="b0a3f-113">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="b0a3f-114">Weitere Informationen finden Sie unter [Abrufen von Informationen, die in Attributen gespeicherte](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c).</span><span class="sxs-lookup"><span data-stu-id="b0a3f-114">For more information, see [Retrieving Information Stored in Attributes](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c).</span></span>  
  
-   <span data-ttu-id="b0a3f-115">Zum Untersuchen und Instanziieren von Typen in einer Assembly.</span><span class="sxs-lookup"><span data-stu-id="b0a3f-115">For examining and instantiating types in an assembly.</span></span>  
  
-   <span data-ttu-id="b0a3f-116">Zum Erstellen neuer Typen zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="b0a3f-116">For building new types at runtime.</span></span> <span data-ttu-id="b0a3f-117">Verwenden Sie die Klassen in <xref:System.Reflection.Emit>.</xref:System.Reflection.Emit></span><span class="sxs-lookup"><span data-stu-id="b0a3f-117">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
-   <span data-ttu-id="b0a3f-118">Zum Ausführen von späten Bindung, die Zugriff auf Methoden in Typen, die zur Laufzeit erstellt.</span><span class="sxs-lookup"><span data-stu-id="b0a3f-118">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="b0a3f-119">Finden Sie unter [dynamisches Laden und Verwenden von Typen](http://msdn.microsoft.com/library/db985bec-5942-40ec-b13a-771ae98623dc).</span><span class="sxs-lookup"><span data-stu-id="b0a3f-119">See the topic [Dynamically Loading and Using Types](http://msdn.microsoft.com/library/db985bec-5942-40ec-b13a-771ae98623dc).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b0a3f-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="b0a3f-120">Related Sections</span></span>  
 <span data-ttu-id="b0a3f-121">Weitere Informationen finden Sie unter: </span><span class="sxs-lookup"><span data-stu-id="b0a3f-121">For more information:</span></span>  
  
-   [<span data-ttu-id="b0a3f-122">Reflektion</span><span class="sxs-lookup"><span data-stu-id="b0a3f-122">Reflection</span></span>](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775)  
  
-   [<span data-ttu-id="b0a3f-123">Anzeigen von Typinformationen</span><span class="sxs-lookup"><span data-stu-id="b0a3f-123">Viewing Type Information</span></span>](http://msdn.microsoft.com/library/7e7303a9-4064-4738-b4e7-b75974ed70d2)  
  
-   [<span data-ttu-id="b0a3f-124">Reflektion und generische Typen</span><span class="sxs-lookup"><span data-stu-id="b0a3f-124">Reflection and Generic Types</span></span>](http://msdn.microsoft.com/library/f7180fc5-dd41-42d4-8a8e-1b34288e06de)  
  
-   <span data-ttu-id="b0a3f-125"><xref:System.Reflection.Emit></xref:System.Reflection.Emit></span><span class="sxs-lookup"><span data-stu-id="b0a3f-125"><xref:System.Reflection.Emit></span></span>  
  
-   [<span data-ttu-id="b0a3f-126">Abrufen von Informationen aus Attributen</span><span class="sxs-lookup"><span data-stu-id="b0a3f-126">Retrieving Information Stored in Attributes</span></span>](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c)  
  
## <a name="see-also"></a><span data-ttu-id="b0a3f-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0a3f-127">See Also</span></span>  
 <span data-ttu-id="b0a3f-128">[Visual Basic-Programmierhandbuch](../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b0a3f-128">[Visual Basic Programming Guide](../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="b0a3f-129"> [Assemblys in der Common Language Runtime](https://msdn.microsoft.com/library/k3677y81)</span><span class="sxs-lookup"><span data-stu-id="b0a3f-129"> [Assemblies in the Common Language Runtime](https://msdn.microsoft.com/library/k3677y81)</span></span>
