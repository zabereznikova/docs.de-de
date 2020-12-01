---
title: Aufrufen einer DLL-Funktion
description: Erfahren Sie mehr zum Aufruf einer DLL-Funktion, der verwirrend erscheinen kann. Der Prozess beim Funktionsaufruf unterscheidet sich je nachdem, ob der Rückgabetyp für Blitting geeignet ist oder nicht.
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- unmanaged functions
- COM interop, platform invoke
- platform invoke, calling unmanaged functions
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
ms.openlocfilehash: 09dd9d30c29660231feee6c624a025ade1fda1d3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96282950"
---
# <a name="calling-a-dll-function"></a><span data-ttu-id="191f9-104">Aufrufen einer DLL-Funktion</span><span class="sxs-lookup"><span data-stu-id="191f9-104">Calling a DLL Function</span></span>

<span data-ttu-id="191f9-105">Obwohl Aufrufe nicht verwalteter DLL-Funktionen nahezu identisch mit anderen Aufrufen von verwaltetem Code sind, bestehen Unterschiede, die DLL-Funktionen zuerst verwirrend erscheinen lassen.</span><span class="sxs-lookup"><span data-stu-id="191f9-105">Although calling unmanaged DLL functions is nearly identical to calling other managed code, there are differences that can make DLL functions seem confusing at first.</span></span> <span data-ttu-id="191f9-106">Dieser Abschnitt enthält Themen, in denen einige ungewöhnliche aufrufbezogene Probleme beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="191f9-106">This section introduces topics that describe some of the unusual calling-related issues.</span></span>  
  
 <span data-ttu-id="191f9-107">Strukturen, die von Plattforminvokeaufrufen zurückgegeben werden, müssen Datentypen sein, die die gleiche Darstellung in verwaltetem und nicht verwaltetem Code haben.</span><span class="sxs-lookup"><span data-stu-id="191f9-107">Structures that are returned from platform invoke calls must be data types that have the same representation in managed and unmanaged code.</span></span> <span data-ttu-id="191f9-108">Solche Typen werden *blitfähige Typen* genannt, da keine Konvertierung erforderlich ist (siehe [Blitfähige und nicht blitfähige Typen](blittable-and-non-blittable-types.md)).</span><span class="sxs-lookup"><span data-stu-id="191f9-108">Such types are called *blittable types* because they do not require conversion (see [Blittable and Non-Blittable Types](blittable-and-non-blittable-types.md)).</span></span> <span data-ttu-id="191f9-109">Um eine Funktion aufzurufen, die über eine nicht blitfähige Struktur als Rückgabetyp verfügt, können Sie einen blitfähigen Hilfstyp mit derselben Größe wie der nicht blitfähige Typ definieren, und nach der Rückgabe der Funktion Daten konvertieren.</span><span class="sxs-lookup"><span data-stu-id="191f9-109">To call a function that has a non-blittable structure as its return type, you can define a blittable helper type of the same size as the non-blittable type and convert the data after the function returns.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="191f9-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="191f9-110">In This Section</span></span>  

 [<span data-ttu-id="191f9-111">Übergeben von Strukturen</span><span class="sxs-lookup"><span data-stu-id="191f9-111">Passing Structures</span></span>](passing-structures.md)  
 <span data-ttu-id="191f9-112">Identifiziert die Probleme der Übergabe von Datenstrukturen mit einem vordefinierten Layout.</span><span class="sxs-lookup"><span data-stu-id="191f9-112">Identifies the issues of passing data structures with a predefined layout.</span></span>  
  
 [<span data-ttu-id="191f9-113">Rückruffunktionen</span><span class="sxs-lookup"><span data-stu-id="191f9-113">Callback Functions</span></span>](callback-functions.md)  
 <span data-ttu-id="191f9-114">Enthält grundlegende Informationen über Rückruffunktionen.</span><span class="sxs-lookup"><span data-stu-id="191f9-114">Provides basic information about callback functions.</span></span>  
  
 [<span data-ttu-id="191f9-115">How to: Implementieren von Rückruffunktionen</span><span class="sxs-lookup"><span data-stu-id="191f9-115">How to: Implement Callback Functions</span></span>](how-to-implement-callback-functions.md)  
 <span data-ttu-id="191f9-116">Beschreibt das Implementieren von Rückruffunktionen in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="191f9-116">Describes how to implement callback functions in managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="191f9-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="191f9-117">Related Sections</span></span>  

 [<span data-ttu-id="191f9-118">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="191f9-118">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)  
 <span data-ttu-id="191f9-119">Beschreibt das Aufrufen von nicht verwalteten DLL-Funktionen mithilfe von Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="191f9-119">Describes how to call unmanaged DLL functions using platform invoke.</span></span>  
  
 [<span data-ttu-id="191f9-120">Marshallen von Daten mit Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="191f9-120">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)  
 <span data-ttu-id="191f9-121">Beschreibt, wie Sie Methodenparameter deklarieren und Argumente an Funktionen übergeben, die aus nicht verwalteten Bibliotheken exportiert wurden.</span><span class="sxs-lookup"><span data-stu-id="191f9-121">Describes how to declare method parameters and pass arguments to functions exported by unmanaged libraries.</span></span>
