---
title: Aufrufen einer DLL-Funktion
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- unmanaged functions
- COM interop, platform invoke
- platform invoke, calling unmanaged functions
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
ms.openlocfilehash: 14589544e05f6c59f4f58f7723fef40e75af9823
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123721"
---
# <a name="calling-a-dll-function"></a><span data-ttu-id="9ecf7-102">Aufrufen einer DLL-Funktion</span><span class="sxs-lookup"><span data-stu-id="9ecf7-102">Calling a DLL Function</span></span>
<span data-ttu-id="9ecf7-103">Obwohl Aufrufe nicht verwalteter DLL-Funktionen nahezu identisch mit anderen Aufrufen von verwaltetem Code sind, bestehen Unterschiede, die DLL-Funktionen zuerst verwirrend erscheinen lassen.</span><span class="sxs-lookup"><span data-stu-id="9ecf7-103">Although calling unmanaged DLL functions is nearly identical to calling other managed code, there are differences that can make DLL functions seem confusing at first.</span></span> <span data-ttu-id="9ecf7-104">Dieser Abschnitt enthält Themen, in denen einige ungewöhnliche aufrufbezogene Probleme beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="9ecf7-104">This section introduces topics that describe some of the unusual calling-related issues.</span></span>  
  
 <span data-ttu-id="9ecf7-105">Strukturen, die von Plattforminvokeaufrufen zurückgegeben werden, müssen Datentypen sein, die die gleiche Darstellung in verwaltetem und nicht verwaltetem Code haben.</span><span class="sxs-lookup"><span data-stu-id="9ecf7-105">Structures that are returned from platform invoke calls must be data types that have the same representation in managed and unmanaged code.</span></span> <span data-ttu-id="9ecf7-106">Solche Typen werden *blitfähige Typen* genannt, da keine Konvertierung erforderlich ist (siehe [Blitfähige und nicht blitfähige Typen](blittable-and-non-blittable-types.md)).</span><span class="sxs-lookup"><span data-stu-id="9ecf7-106">Such types are called *blittable types* because they do not require conversion (see [Blittable and Non-Blittable Types](blittable-and-non-blittable-types.md)).</span></span> <span data-ttu-id="9ecf7-107">Um eine Funktion aufzurufen, die über eine nicht blitfähige Struktur als Rückgabetyp verfügt, können Sie einen blitfähigen Hilfstyp mit derselben Größe wie der nicht blitfähige Typ definieren, und nach der Rückgabe der Funktion Daten konvertieren.</span><span class="sxs-lookup"><span data-stu-id="9ecf7-107">To call a function that has a non-blittable structure as its return type, you can define a blittable helper type of the same size as the non-blittable type and convert the data after the function returns.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9ecf7-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9ecf7-108">In This Section</span></span>  
 [<span data-ttu-id="9ecf7-109">Übergeben von Strukturen</span><span class="sxs-lookup"><span data-stu-id="9ecf7-109">Passing Structures</span></span>](passing-structures.md)  
 <span data-ttu-id="9ecf7-110">Identifiziert die Probleme der Übergabe von Datenstrukturen mit einem vordefinierten Layout.</span><span class="sxs-lookup"><span data-stu-id="9ecf7-110">Identifies the issues of passing data structures with a predefined layout.</span></span>  
  
 [<span data-ttu-id="9ecf7-111">Rückruffunktionen</span><span class="sxs-lookup"><span data-stu-id="9ecf7-111">Callback Functions</span></span>](callback-functions.md)  
 <span data-ttu-id="9ecf7-112">Enthält grundlegende Informationen über Rückruffunktionen.</span><span class="sxs-lookup"><span data-stu-id="9ecf7-112">Provides basic information about callback functions.</span></span>  
  
 [<span data-ttu-id="9ecf7-113">How to: Implementieren von Rückruffunktionen</span><span class="sxs-lookup"><span data-stu-id="9ecf7-113">How to: Implement Callback Functions</span></span>](how-to-implement-callback-functions.md)  
 <span data-ttu-id="9ecf7-114">Beschreibt das Implementieren von Rückruffunktionen in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="9ecf7-114">Describes how to implement callback functions in managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9ecf7-115">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="9ecf7-115">Related Sections</span></span>  
 [<span data-ttu-id="9ecf7-116">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="9ecf7-116">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)  
 <span data-ttu-id="9ecf7-117">Beschreibt das Aufrufen von nicht verwalteten DLL-Funktionen mithilfe von Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="9ecf7-117">Describes how to call unmanaged DLL functions using platform invoke.</span></span>  
  
 [<span data-ttu-id="9ecf7-118">Marshallen von Daten mit Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="9ecf7-118">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)  
 <span data-ttu-id="9ecf7-119">Beschreibt, wie Sie Methodenparameter deklarieren und Argumente an Funktionen übergeben, die aus nicht verwalteten Bibliotheken exportiert wurden.</span><span class="sxs-lookup"><span data-stu-id="9ecf7-119">Describes how to declare method parameters and pass arguments to functions exported by unmanaged libraries.</span></span>
