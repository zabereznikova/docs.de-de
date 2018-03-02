---
title: Behandeln von COM-Interop-Ausnahmen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: error-reference
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- HRESULTs
- exceptions, COM interop
- COM interop, exceptions
ms.assetid: e6104aa8-8e5f-4069-b864-def85579c96c
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e894d07e77b929b1ea22df2d34e542544ec3b1f3
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="handling-com-interop-exceptions"></a>Behandeln von COM-Interop-Ausnahmen
Verwalteter und nicht verwalteter Code können zusammenarbeiten, um Ausnahmen zu behandeln. Wenn eine Methode in verwaltetem Code eine Ausnahme auslöst, kann die Common Language Runtime ein HRESULT an ein COM-Objekt übergeben. Wenn eine Methode in nicht verwaltetem Code fehlschlägt, indem ein Fehler-HRESULT zurückgegeben wird, löst die Common Language Runtime eine Ausnahme aus, die von verwaltetem Code abgefangen werden kann.  
  
 Die Common Language Runtime ordnet das HRESULT von COM-Interop automatisch zu spezifischeren Ausnahmen zu. So wird z. B. E_ACCESSDENIED zu <xref:System.UnauthorizedAccessException>, E_OUTOFMEMORY zu <xref:System.OutOfMemoryException> usw.  
  
 Wenn HRESULT ein benutzerdefiniertes Ergebnis wird oder es zur Laufzeit unbekannt ist, übergibt die Common Language Runtime ein generisches <xref:System.Runtime.InteropServices.COMException> an den Client. Die **ErrorCode**-Eigenschaft von **COMException** enthält den HRESULT-Wert.  
  
## <a name="working-with-ierrorinfo"></a>Arbeiten mit IErrorInfo  
 Wenn ein Fehler von COM an verwalteten Code übergeben wird, füllt die Common Language Runtime das Ausnahmeobjekt mit Fehlerinformationen. COM-Objekte, die "IErrorInfo" unterstützen und HRESULTS zurückgeben, stellen diese Informationen für Ausnahmen in verwaltetem Code bereit. Die Common Language Runtime ordnet die Beschreibung des COM-Fehlers zur <xref:System.Exception.Message%2A>-Eigenschaft der Ausnahme zu. Wenn HRESULT keine weiteren Fehlerinformationen bereitstellt, füllt die Common Language Runtime viele Eigenschaften der Ausnahme mit Standardwerten.  
  
 Wenn eine Methode in nicht verwaltetem Code fehlschlägt, kann eine Ausnahme an ein verwaltetes Codesegment übergeben werden. Das Thema [HRESULTS und Ausnahmen](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md) enthält eine Tabelle mit Zuordnungen von HRESULTS zu Ausnahmeobjekten der Common Language Runtime.  

## <a name="see-also"></a>Siehe auch
[Ausnahmen](index.md) 
