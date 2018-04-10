---
title: Tlbexp-Hilfsfunktionen (Referenz zur nicht verwalteten API)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8a9d483e101fdb94a43055b6081fcc31a458a1ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a>Tlbexp-Hilfsfunktionen (Referenz zur nicht verwalteten API)
Die [Type Library Exporter-Tool](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) lädt eine dynamic Link Library, die mit dem Namen TlbRef.dll. Diese DLL enthält die beiden Hilfsfunktionen und eine Schnittstelle, die die Exportertool während der Konvertierung der Assembly in eine Bibliothek verwendet.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [GetTypeLibInfo-Funktion](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 Bietet Lokalisierung und Betriebssystem für eine Typbibliothek.  
  
 [LoadTypeLibWithResolver-Funktion](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 Lädt eine Typbibliothek mit einer Implementierung von der [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) zum Auflösen einer beliebigen referenzierte Typbibliotheken.  
  
 [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 Stellt die [ResolveTypeLib-Methode](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), die den vollqualifizierten Pfad einer Typbibliothek zurückgibt.
