---
title: Debuggen von globalen statischen Funktionen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- global static functions [.NET Framework debugging]
- debugging global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], debugging
ms.assetid: efc64414-77c3-48d0-881a-8594ed416aad
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7fde0941959619f4832019806401be0ffddb81e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-global-static-functions"></a><span data-ttu-id="01d62-102">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="01d62-102">Debugging Global Static Functions</span></span>
<span data-ttu-id="01d62-103">In diesem Abschnitt werden die nicht verwalteten globalen statischen Funktionen beschrieben, die die Debug-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="01d62-103">This section describes the unmanaged global static functions that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="01d62-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="01d62-104">In This Section</span></span>  
 [<span data-ttu-id="01d62-105">_EFN_GetManagedExcepStack-Funktion</span><span class="sxs-lookup"><span data-stu-id="01d62-105">_EFN_GetManagedExcepStack Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedexcepstack-function.md)  
 <span data-ttu-id="01d62-106">Gibt bei Angabe der Adresse eines verwalteten Ausnahmeobjekts eine Zeichenfolgenversion der enthaltenen Stapelüberwachung zurück.</span><span class="sxs-lookup"><span data-stu-id="01d62-106">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
 [<span data-ttu-id="01d62-107">_EFN_GetManagedObjectFieldInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="01d62-107">_EFN_GetManagedObjectFieldInfo Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedobjectfieldinfo-function.md)  
 <span data-ttu-id="01d62-108">Ruft den Offset vom Beginn eines Objekts zu einem Feld sowie den Wert des Felds mit dem bereitgestellten Objektzeiger und Feldnamen ab.</span><span class="sxs-lookup"><span data-stu-id="01d62-108">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
 [<span data-ttu-id="01d62-109">_EFN_GetManagedObjectName-Funktion</span><span class="sxs-lookup"><span data-stu-id="01d62-109">_EFN_GetManagedObjectName Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedobjectname-function.md)  
 <span data-ttu-id="01d62-110">Ruft den Namen eines Typs mit dem bereitgestellten verwalteten Objektzeiger ab.</span><span class="sxs-lookup"><span data-stu-id="01d62-110">Gets the name of a type by using the provided managed object pointer.</span></span>  
  
 [<span data-ttu-id="01d62-111">_EFN_StackTrace-Funktion</span><span class="sxs-lookup"><span data-stu-id="01d62-111">_EFN_StackTrace Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/efn-stacktrace-function.md)  
 <span data-ttu-id="01d62-112">Stellt eine Textdarstellung einer verwalteten Stapelüberwachung und ein Array von `CONTEXT`-Datensätzen bereit, einen Datensatz für jeden Übergang zwischen nicht verwaltetem und verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="01d62-112">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
 [<span data-ttu-id="01d62-113">CLRDataCreateInstance-Funktion</span><span class="sxs-lookup"><span data-stu-id="01d62-113">CLRDataCreateInstance Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatacreateinstance-function.md)  
 <span data-ttu-id="01d62-114">Wird von den Datenzugriffsdiensten der Common Language Runtime (CLR) aufgerufen, um das angegebene Schnittstellenobjekt für den angegebenen Zielprozess zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="01d62-114">Called by the common language runtime (CLR) data access services to create the specified interface object for the specified target process.</span></span>  
  
 [<span data-ttu-id="01d62-115">PFN_CLRDataCreateInstance-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="01d62-115">PFN_CLRDataCreateInstance Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/debugging/pfn-clrdatacreateinstance-function-pointer.md)  
 <span data-ttu-id="01d62-116">Verweist auf eine Funktion, die von den Datenzugriffsdiensten der Common Language Runtime (CLR) aufgerufen wird, um das angegebene Schnittstellenobjekt für den angegebenen Zielprozess zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="01d62-116">Points to a function that is called by the CLR data access services to create the specified interface object for the specified target process.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="01d62-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="01d62-117">Related Sections</span></span>  
 [<span data-ttu-id="01d62-118">Debuggen von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="01d62-118">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="01d62-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="01d62-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [<span data-ttu-id="01d62-120">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="01d62-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [<span data-ttu-id="01d62-121">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="01d62-121">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
