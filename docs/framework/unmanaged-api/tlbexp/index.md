---
title: Tlbexp-Hilfsfunktionen (Referenz zur nicht verwalteten API)
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f41a233e9b5338bdb0a324ff9af267a97821d4e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455872"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="4c87e-102">Tlbexp-Hilfsfunktionen (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="4c87e-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>
<span data-ttu-id="4c87e-103">Die [Type Library Exporter-Tool](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) lädt eine dynamic Link Library, die mit dem Namen TlbRef.dll.</span><span class="sxs-lookup"><span data-stu-id="4c87e-103">The [Type Library Exporter tool](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="4c87e-104">Diese DLL enthält die beiden Hilfsfunktionen und eine Schnittstelle, die die Exportertool während der Konvertierung der Assembly in eine Bibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="4c87e-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c87e-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4c87e-105">In This Section</span></span>  
 [<span data-ttu-id="4c87e-106">GetTypeLibInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="4c87e-106">GetTypeLibInfo Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 <span data-ttu-id="4c87e-107">Bietet Lokalisierung und Betriebssystem für eine Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="4c87e-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="4c87e-108">LoadTypeLibWithResolver-Funktion</span><span class="sxs-lookup"><span data-stu-id="4c87e-108">LoadTypeLibWithResolver Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 <span data-ttu-id="4c87e-109">Lädt eine Typbibliothek mit einer Implementierung von der [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) zum Auflösen einer beliebigen referenzierte Typbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="4c87e-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="4c87e-110">ITypeLibResolver-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4c87e-110">ITypeLibResolver Interface</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 <span data-ttu-id="4c87e-111">Stellt die [ResolveTypeLib-Methode](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), die den vollqualifizierten Pfad einer Typbibliothek zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4c87e-111">Provides the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>
