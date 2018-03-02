---
title: "Threadsicherheit in regulären Ausdrücken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework regular expressions, threads
- regular expressions, threads
- searching with regular expressions, threads
- parsing text with regular expressions, threads
- pattern-matching with regular expressions, threads
ms.assetid: 7c4a167b-5236-4cde-a2ca-58646230730f
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 804f83d85206b5f49a0bea290f281b36e18bb847
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="thread-safety-in-regular-expressions"></a><span data-ttu-id="c3cf2-102">Threadsicherheit in regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="c3cf2-102">Thread Safety in Regular Expressions</span></span>
<span data-ttu-id="c3cf2-103">Die <xref:System.Text.RegularExpressions.Regex>-Klasse selbst ist threadsicher und nicht änderbar (schreibgeschützt).</span><span class="sxs-lookup"><span data-stu-id="c3cf2-103">The <xref:System.Text.RegularExpressions.Regex> class itself is thread safe and immutable (read-only).</span></span> <span data-ttu-id="c3cf2-104">**Regex**-Objekte können also in jedem Thread erzeugt und von mehreren Threads gemeinsam genutzt werden. Übereinstimmende Methoden können von jedem Thread aufgerufen werden und ändern keinen globalen Zustand.</span><span class="sxs-lookup"><span data-stu-id="c3cf2-104">That is, **Regex** objects can be created on any thread and shared between threads; matching methods can be called from any thread and never alter any global state.</span></span>  
  
 <span data-ttu-id="c3cf2-105">Ergebnisobjekte (**Match** und **MatchCollection**), die von **Regex** zurückgegeben werden, sollten allerdings in einem einzelnen Thread verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c3cf2-105">However, result objects (**Match** and **MatchCollection**) returned by **Regex** should be used on a single thread.</span></span> <span data-ttu-id="c3cf2-106">Obwohl viele dieser Objekte logisch nicht änderbar sind, können ihre Implementierungen die Berechnung einiger Ergebnisse zur Verbesserung der Leistung verzögern. Daher müssen Aufrufer den Zugriff darauf serialisieren.</span><span class="sxs-lookup"><span data-stu-id="c3cf2-106">Although many of these objects are logically immutable, their implementations could delay computation of some results to improve performance, and as a result, callers must serialize access to them.</span></span>  
  
 <span data-ttu-id="c3cf2-107">Wenn **Regex**-Ergebnisobjekte in mehreren Threads gemeinsam genutzt werden müssen, können diese Objekte durch den Aufruf ihrer synchronisierten Methoden in threadsichere Instanzen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="c3cf2-107">If there is a need to share **Regex** result objects on multiple threads, these objects can be converted to thread-safe instances by calling their synchronized methods.</span></span> <span data-ttu-id="c3cf2-108">Mit Ausnahme von Enumeratoren sind alle Klassen für reguläre Ausdrücke threadsicher oder können von einer synchronisierten Methode in threadsichere Objekte konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="c3cf2-108">With the exception of enumerators, all regular expression classes are thread safe or can be converted into thread-safe objects by a synchronized method.</span></span>  
  
 <span data-ttu-id="c3cf2-109">Enumeratoren sind die einzige Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="c3cf2-109">Enumerators are the only exception.</span></span> <span data-ttu-id="c3cf2-110">Eine Anwendung muss Aufrufe von Sammlungsenumeratoren serialisieren.</span><span class="sxs-lookup"><span data-stu-id="c3cf2-110">An application must serialize calls to collection enumerators.</span></span> <span data-ttu-id="c3cf2-111">Die Regel ist, dass für eine Sammlung, die in mehr als einem Thread gleichzeitig als Enumeration verwendet werden kann, die Enumeratormethoden im Stammobjekt der Sammlung, die der Enumerator durchläuft, synchronisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c3cf2-111">The rule is that if a collection can be enumerated on more than one thread simultaneously, you should synchronize enumerator methods on the root object of the collection traversed by the enumerator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3cf2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3cf2-112">See Also</span></span>  
 [<span data-ttu-id="c3cf2-113">Reguläre Ausdrücke in .NET</span><span class="sxs-lookup"><span data-stu-id="c3cf2-113">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
