---
title: Tlbexp-Hilfsfunktionen (Referenz zur nicht verwalteten API)
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
ms.openlocfilehash: cbde2af9c8a03e6c41f571120027030713f1b8d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73104124"
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
