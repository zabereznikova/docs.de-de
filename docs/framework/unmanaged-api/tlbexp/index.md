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
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a>Tlbexp-Hilfsfunktionen (Referenz zur nicht verwalteten API)

Das [Exportwerkzeug für die Typbibliothek](../../tools/tlbexp-exe-type-library-exporter.md). (Tlbexp.exe) lädt eine dynamische Linkbibliothek namens TlbRef.dll. Diese DLL enthält zwei Hilfsfunktionen und eine Schnittstelle, die das Exportwerkzeug während der Konvertierung der Assembly in eine Typbibliothek verwendet.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [GetTypeLibInfo-Funktion](gettypelibinfo-function.md)  
 Bietet Lokalisierungs- und Betriebssysteminformationen für eine Typbibliothek.  
  
 [LoadTypeLibWithResolver-Funktion](loadtypelibwithresolver-function.md)  
 Lädt eine Typbibliothek unter Verwendung einer Implementierung der Schnittstelle [ITypeLibResolver](itypelibresolver-interface.md), um alle referenzierten Typbibliotheken aufzulösen.  
  
 [ITypeLibResolver-Schnittstelle](itypelibresolver-interface.md)  
 Stellt die Methode [ResolveTypeLib](resolvetypelib-method.md) bereit, die den voll qualifizierten Pfad einer Typbibliothek zurückgibt.
