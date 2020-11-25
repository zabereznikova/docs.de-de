---
title: Tlbexp-Hilfsfunktionen (Referenz zur nicht verwalteten API)
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
ms.openlocfilehash: 9386918f3574720d90bda7e8da592fa0c91160e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708243"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="1bc60-102">Tlbexp-Hilfsfunktionen (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="1bc60-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>

<span data-ttu-id="1bc60-103">Das [Exportwerkzeug für die Typbibliothek](../../tools/tlbexp-exe-type-library-exporter.md). (Tlbexp.exe) lädt eine dynamische Linkbibliothek namens TlbRef.dll.</span><span class="sxs-lookup"><span data-stu-id="1bc60-103">The [Type Library Exporter tool](../../tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="1bc60-104">Diese DLL enthält zwei Hilfsfunktionen und eine Schnittstelle, die das Exportwerkzeug während der Konvertierung der Assembly in eine Typbibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="1bc60-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1bc60-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1bc60-105">In This Section</span></span>  

 [<span data-ttu-id="1bc60-106">GetTypeLibInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="1bc60-106">GetTypeLibInfo Function</span></span>](gettypelibinfo-function.md)  
 <span data-ttu-id="1bc60-107">Bietet Lokalisierungs- und Betriebssysteminformationen für eine Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="1bc60-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="1bc60-108">LoadTypeLibWithResolver-Funktion</span><span class="sxs-lookup"><span data-stu-id="1bc60-108">LoadTypeLibWithResolver Function</span></span>](loadtypelibwithresolver-function.md)  
 <span data-ttu-id="1bc60-109">Lädt eine Typbibliothek unter Verwendung einer Implementierung der Schnittstelle [ITypeLibResolver](itypelibresolver-interface.md), um alle referenzierten Typbibliotheken aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="1bc60-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="1bc60-110">ITypeLibResolver-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1bc60-110">ITypeLibResolver Interface</span></span>](itypelibresolver-interface.md)  
 <span data-ttu-id="1bc60-111">Stellt die Methode [ResolveTypeLib](resolvetypelib-method.md) bereit, die den voll qualifizierten Pfad einer Typbibliothek zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="1bc60-111">Provides the [ResolveTypeLib method](resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>
