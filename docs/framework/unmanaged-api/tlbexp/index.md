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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967699"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="05a12-102">Tlbexp-Hilfsfunktionen (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="05a12-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>
<span data-ttu-id="05a12-103">Das [Exportwerkzeug für die Typbibliothek](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md). (Tlbexp.exe) lädt eine dynamische Linkbibliothek namens TlbRef.dll.</span><span class="sxs-lookup"><span data-stu-id="05a12-103">The [Type Library Exporter tool](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="05a12-104">Diese DLL enthält zwei Hilfsfunktionen und eine Schnittstelle, die das Exportwerkzeug während der Konvertierung der Assembly in eine Typbibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="05a12-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="05a12-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="05a12-105">In This Section</span></span>  
 [<span data-ttu-id="05a12-106">GetTypeLibInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="05a12-106">GetTypeLibInfo Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 <span data-ttu-id="05a12-107">Bietet Lokalisierungs- und Betriebssysteminformationen für eine Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="05a12-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="05a12-108">LoadTypeLibWithResolver-Funktion</span><span class="sxs-lookup"><span data-stu-id="05a12-108">LoadTypeLibWithResolver Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 <span data-ttu-id="05a12-109">Lädt eine Typbibliothek unter Verwendung einer Implementierung der Schnittstelle [ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), um alle referenzierten Typbibliotheken aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="05a12-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="05a12-110">ITypeLibResolver-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="05a12-110">ITypeLibResolver Interface</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 <span data-ttu-id="05a12-111">Stellt die Methode [ResolveTypeLib](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) bereit, die den voll qualifizierten Pfad einer Typbibliothek zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="05a12-111">Provides the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>
