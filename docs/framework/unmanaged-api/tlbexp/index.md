---
title: Tlbexp-Hilfsfunktionen (Referenz zur nicht verwalteten API)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d5d0a0b08be725a50442a3db9f9942bceea7cf8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="9d1ed-102">Tlbexp-Hilfsfunktionen (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="9d1ed-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>
<span data-ttu-id="9d1ed-103">Die [Type Library Exporter-Tool](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) lädt eine dynamic Link Library, die mit dem Namen TlbRef.dll.</span><span class="sxs-lookup"><span data-stu-id="9d1ed-103">The [Type Library Exporter tool](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="9d1ed-104">Diese DLL enthält die beiden Hilfsfunktionen und eine Schnittstelle, die die Exportertool während der Konvertierung der Assembly in eine Bibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="9d1ed-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9d1ed-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9d1ed-105">In This Section</span></span>  
 [<span data-ttu-id="9d1ed-106">GetTypeLibInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="9d1ed-106">GetTypeLibInfo Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 <span data-ttu-id="9d1ed-107">Bietet Lokalisierung und Betriebssystem für eine Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="9d1ed-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="9d1ed-108">LoadTypeLibWithResolver-Funktion</span><span class="sxs-lookup"><span data-stu-id="9d1ed-108">LoadTypeLibWithResolver Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 <span data-ttu-id="9d1ed-109">Lädt eine Typbibliothek mit einer Implementierung von der [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) zum Auflösen einer beliebigen referenzierte Typbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="9d1ed-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="9d1ed-110">ITypeLibResolver-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9d1ed-110">ITypeLibResolver Interface</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 <span data-ttu-id="9d1ed-111">Stellt die [ResolveTypeLib-Methode](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), die den vollqualifizierten Pfad einer Typbibliothek zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9d1ed-111">Provides the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>
