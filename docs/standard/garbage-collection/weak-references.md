---
title: Schwache Verweise
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- weak references, short
- weak references, using
- weak references, long
- garbage collection, weak references
ms.assetid: 6a600fe5-3af3-4c64-82da-10a0a8e2d79b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 906c23caa7065486bb094ad2475ed9e7e24b3d9c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="weak-references"></a><span data-ttu-id="b25e5-102">Schwache Verweise</span><span class="sxs-lookup"><span data-stu-id="b25e5-102">Weak References</span></span>
<span data-ttu-id="b25e5-103">Der Garbage Collector kann kein Objekt sammeln, das von einer Anwendung verwendet wird, während der Anwendungscode dieses Objekt erreichen kann.</span><span class="sxs-lookup"><span data-stu-id="b25e5-103">The garbage collector cannot collect an object in use by an application while the application's code can reach that object.</span></span> <span data-ttu-id="b25e5-104">Dies wird als starker Verweis der Anwendung auf das Objekt bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b25e5-104">The application is said to have a strong reference to the object.</span></span>  
  
 <span data-ttu-id="b25e5-105">Bei einem schwachen Verweis kann der Garbage Collector das Objekt sammeln, während die Anwendung nach wie vor auf das Objekt zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="b25e5-105">A weak reference permits the garbage collector to collect the object while still allowing the application to access the object.</span></span> <span data-ttu-id="b25e5-106">Ein schwacher Verweis ist nur während der unbestimmten Zeitspanne gültig, bis das Objekt gesammelt wurde, wenn keine starken Verweise vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b25e5-106">A weak reference is valid only during the indeterminate amount of time until the object is collected when no strong references exist.</span></span> <span data-ttu-id="b25e5-107">Wenn Sie einen schwachen Verweis verwenden, kann die Anwendung immer noch einen starken Verweis auf das Objekt erhalten, sodass es nicht gesammelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b25e5-107">When you use a weak reference, the application can still obtain a strong reference to the object, which prevents it from being collected.</span></span> <span data-ttu-id="b25e5-108">Es besteht jedoch immer das Risiko, dass der Garbage Collector das Objekt zuerst erreicht, bevor ein starker Verweis erneut hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b25e5-108">However, there is always the risk that the garbage collector will get to the object first before a strong reference is reestablished.</span></span>  
  
 <span data-ttu-id="b25e5-109">Schwache Verweise sind hilfreich für Objekte, die viel Speicher belegen, aber leicht wieder erstellt werden können, wenn sie von der Garbage Collection freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b25e5-109">Weak references are useful for objects that use a lot of memory, but can be recreated easily if they are reclaimed by garbage collection.</span></span>  
  
 <span data-ttu-id="b25e5-110">Angenommen Sie, eine Strukturansicht, in einer Windows Forms-Anwendung eine komplexe hierarchische Auswahl von Optionen für den Benutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b25e5-110">Suppose a tree view in a Windows Forms application displays a complex hierarchical choice of options to the user.</span></span> <span data-ttu-id="b25e5-111">Wenn die zugrunde liegenden Daten umfangreich sind, ist es ineffizient, die Strukturansicht im Speicher zu behalten, wenn der Benutzer mit einem anderen Teil der Anwendung beschäftigt ist.</span><span class="sxs-lookup"><span data-stu-id="b25e5-111">If the underlying data is large, keeping the tree in memory is inefficient when the user is involved with something else in the application.</span></span>  
  
 <span data-ttu-id="b25e5-112">Wenn der Benutzer sofort auf einen anderen Teil der Anwendung gewechselt wird, können Sie die <xref:System.WeakReference> Klasse erstellen einen schwachen Verweis auf die Struktur und alle starken Verweise zerstören.</span><span class="sxs-lookup"><span data-stu-id="b25e5-112">When the user switches away to another part of the application, you can use the <xref:System.WeakReference> class to create a weak reference to the tree and destroy all strong references.</span></span> <span data-ttu-id="b25e5-113">Wenn der Benutzer wieder zur Strukturansicht zurückwechselt, versucht die Anwendung, einen starken Verweis auf die Strukturansicht zu erhalten und vermeidet, wenn dies gelingt, eine Neuerstellung der Strukturansicht.</span><span class="sxs-lookup"><span data-stu-id="b25e5-113">When the user switches back to the tree, the application attempts to obtain a strong reference to the tree and, if successful, avoids reconstructing the tree.</span></span>  
  
 <span data-ttu-id="b25e5-114">Um einen schwachen Verweis mit einem Objekt einzurichten, erstellen Sie eine <xref:System.WeakReference> mit der Instanz des Objekts nachverfolgt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b25e5-114">To establish a weak reference with an object, you create a <xref:System.WeakReference> using the instance of the object to be tracked.</span></span> <span data-ttu-id="b25e5-115">Legen Sie Sie dann die <xref:System.WeakReference.Target%2A> -Eigenschaft auf dieses Objekt und die ursprüngliche einen Verweis auf das Objekt, das `null`.</span><span class="sxs-lookup"><span data-stu-id="b25e5-115">You then set the <xref:System.WeakReference.Target%2A> property to that object and set the original reference to the object to `null`.</span></span> <span data-ttu-id="b25e5-116">Ein Codebeispiel finden Sie unter <xref:System.WeakReference> in der Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="b25e5-116">For a code example, see <xref:System.WeakReference> in the class library.</span></span>  
  
## <a name="short-and-long-weak-references"></a><span data-ttu-id="b25e5-117">Kurze und lange schwache Verweise</span><span class="sxs-lookup"><span data-stu-id="b25e5-117">Short and Long Weak References</span></span>  
 <span data-ttu-id="b25e5-118">Sie können einen kurzen schwachen Verweis oder einen langen schwachen Verweis erstellen:</span><span class="sxs-lookup"><span data-stu-id="b25e5-118">You can create a short weak reference or a long weak reference:</span></span>  
  
-   <span data-ttu-id="b25e5-119">Short</span><span class="sxs-lookup"><span data-stu-id="b25e5-119">Short</span></span>  
  
     <span data-ttu-id="b25e5-120">Das Ziel eines kurzen schwachen Verweises wird `null`, wenn das Objekt von der Garbage Collection freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b25e5-120">The target of a short weak reference becomes `null` when the object is reclaimed by garbage collection.</span></span> <span data-ttu-id="b25e5-121">Der schwache Verweis ist selbst ein verwaltetes Objekt und unterliegt wie jedes andere verwaltete Objekt der Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b25e5-121">The weak reference is itself a managed object, and is subject to garbage collection just like any other managed object.</span></span>  <span data-ttu-id="b25e5-122">Ein kurzer schwacher Verweis ist der Standardkonstruktor für <xref:System.WeakReference>.</span><span class="sxs-lookup"><span data-stu-id="b25e5-122">A short weak reference is the default constructor for <xref:System.WeakReference>.</span></span>  
  
-   <span data-ttu-id="b25e5-123">Long</span><span class="sxs-lookup"><span data-stu-id="b25e5-123">Long</span></span>  
  
     <span data-ttu-id="b25e5-124">Ein schwacher Verweis wird beibehalten, nach der objektspezifischen <xref:System.Object.Finalize%2A> -Methode aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="b25e5-124">A long weak reference is retained after the object's <xref:System.Object.Finalize%2A> method has been called.</span></span> <span data-ttu-id="b25e5-125">Dadurch kann das Objekt neu erstellt werden, aber der Zustand des Objekts bleibt unvorhersehbar.</span><span class="sxs-lookup"><span data-stu-id="b25e5-125">This allows the object to be recreated, but the state of the object remains unpredictable.</span></span> <span data-ttu-id="b25e5-126">Um einen langen Verweis zu verwenden, geben `true` in die <xref:System.WeakReference> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="b25e5-126">To use a long reference, specify `true` in the <xref:System.WeakReference> constructor.</span></span>  
  
     <span data-ttu-id="b25e5-127">Wenn der Typ des Objekts keine <xref:System.Object.Finalize%2A> -Methode, die Funktionen des kurzen schwachen Verweises angewendet, und der schwache Verweis ist nur dann gültig, bis das Ziel gesammelt werden, die auftreten kann, können Sie jederzeit nach der Finalizer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b25e5-127">If the object's type does not have a <xref:System.Object.Finalize%2A> method, the short weak reference functionality applies and the weak reference is valid only until the target is collected, which can occur anytime after the finalizer is run.</span></span>  
  
 <span data-ttu-id="b25e5-128">Um einen starken Verweis herstellen und das Objekt erneut zu verwenden, wandeln Sie die <xref:System.WeakReference.Target%2A> Eigenschaft eine <xref:System.WeakReference> in den Typ des Objekts.</span><span class="sxs-lookup"><span data-stu-id="b25e5-128">To establish a strong reference and use the object again, cast the <xref:System.WeakReference.Target%2A> property of a <xref:System.WeakReference> to the type of the object.</span></span> <span data-ttu-id="b25e5-129">Wenn die <xref:System.WeakReference.Target%2A> -Eigenschaft gibt `null`, das Objekt wurde, andernfalls gesammelt, Sie können weiterhin das Objekt zu verwenden, da die Anwendung einen starken Verweis darauf wiederhergestellt hat.</span><span class="sxs-lookup"><span data-stu-id="b25e5-129">If the <xref:System.WeakReference.Target%2A> property returns `null`, the object was collected; otherwise, you can continue to use the object because the application has regained a strong reference to it.</span></span>  
  
## <a name="guidelines-for-using-weak-references"></a><span data-ttu-id="b25e5-130">Richtlinien für die Verwendung von schwachen Verweisen</span><span class="sxs-lookup"><span data-stu-id="b25e5-130">Guidelines for Using Weak References</span></span>  
 <span data-ttu-id="b25e5-131">Verwenden Sie lange schwache Verweise nur, wenn dies notwendig ist, da der Zustand des Objekts nach Abschluss unvorhersehbar ist.</span><span class="sxs-lookup"><span data-stu-id="b25e5-131">Use long weak references only when necessary as the state of the object is unpredictable after finalization.</span></span>  
  
 <span data-ttu-id="b25e5-132">Vermeiden Sie, schwache Verweise auf kleine Objekte zu verwenden, da der Zeiger selbst möglicherweise genauso groß oder größer ist.</span><span class="sxs-lookup"><span data-stu-id="b25e5-132">Avoid using weak references to small objects because the pointer itself may be as large or larger.</span></span>  
  
 <span data-ttu-id="b25e5-133">Vermeiden Sie, schwache Verweise als automatische Lösung für Speicherverwaltungsprobleme zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b25e5-133">Avoid using weak references as an automatic solution to memory management problems.</span></span> <span data-ttu-id="b25e5-134">Entwickeln Sie stattdessen eine wirksame Richtlinie zum Zwischenspeichern für die Behandlung von Objekten der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b25e5-134">Instead, develop an effective caching policy for handling your application's objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b25e5-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b25e5-135">See Also</span></span>  
 [<span data-ttu-id="b25e5-136">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="b25e5-136">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
