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
ms.openlocfilehash: a95ff535a4d0847fbd4b8af28f873b67a1829a4f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798825"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a>Tlbexp-Hilfsfunktionen (Referenz zur nicht verwalteten API)
Das [Exportwerkzeug für die Typbibliothek](../../tools/tlbexp-exe-type-library-exporter.md). (Tlbexp.exe) lädt eine dynamische Linkbibliothek namens TlbRef.dll. Diese DLL enthält zwei Hilfsfunktionen und eine Schnittstelle, die das Exportwerkzeug während der Konvertierung der Assembly in eine Typbibliothek verwendet.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [GetTypeLibInfo-Funktion](gettypelibinfo-function.md)  
 Bietet Lokalisierungs- und Betriebssysteminformationen für eine Typbibliothek.  
  
 [LoadTypeLibWithResolver-Funktion](loadtypelibwithresolver-function.md)  
 Lädt eine Typbibliothek unter Verwendung einer Implementierung der Schnittstelle [ITypeLibResolver](itypelibresolver-interface.md), um alle referenzierten Typbibliotheken aufzulösen.  
  
 [ITypeLibResolver-Schnittstelle](itypelibresolver-interface.md)  
 Stellt die Methode [ResolveTypeLib](resolvetypelib-method.md) bereit, die den voll qualifizierten Pfad einer Typbibliothek zurückgibt.
