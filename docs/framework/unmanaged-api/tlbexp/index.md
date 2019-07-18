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
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a>Tlbexp-Hilfsfunktionen (Referenz zur nicht verwalteten API)
Das [Exportwerkzeug für die Typbibliothek](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md). (Tlbexp.exe) lädt eine dynamische Linkbibliothek namens TlbRef.dll. Diese DLL enthält zwei Hilfsfunktionen und eine Schnittstelle, die das Exportwerkzeug während der Konvertierung der Assembly in eine Typbibliothek verwendet.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [GetTypeLibInfo-Funktion](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 Bietet Lokalisierungs- und Betriebssysteminformationen für eine Typbibliothek.  
  
 [LoadTypeLibWithResolver-Funktion](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 Lädt eine Typbibliothek unter Verwendung einer Implementierung der Schnittstelle [ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), um alle referenzierten Typbibliotheken aufzulösen.  
  
 [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 Stellt die Methode [ResolveTypeLib](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) bereit, die den voll qualifizierten Pfad einer Typbibliothek zurückgibt.
