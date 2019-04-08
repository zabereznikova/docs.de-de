---
title: dllMainReturnsFalse-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), DllMain returns false
- DllMainReturnsFalse MDA
- DllMain function
- MDAs (managed debugging assistants), DllMain returns false
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fd987cea78d082eee26032d5f98a54dc0cd3e1d5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072622"
---
# <a name="dllmainreturnsfalse-mda"></a>dllMainReturnsFalse-MDA
Der Assistent für verwaltetes Debuggen `dllMainReturnsFalse` (Managed Debugging Assistant, MDA) wird aktiviert, wenn die verwaltete Funktion `DllMain` einer Benutzerassembly, die mit der Ursache DLL_PROCESS_ATTACH aufgerufen wurde, FALSE zurückgibt.  
  
## <a name="symptoms"></a>Symptome  
 Die Funktion `DllMain` gab FALSE zurück, um anzuzeigen, dass sie nicht ordnungsgemäß ausgeführt wurde. Dies kann zu unbestimmten Problemen führen, da `DllMain`-Funktionen in der Regel wichtige Initialisierungscodes enthalten.  
  
## <a name="cause"></a>Ursache  
 Die Funktion `DllMain` wird zur DLL-Initialisierung mit der Ursache DLL_PROCESS_ATTACH beim Laden aufgerufen. Wird FALSE zurückgegeben, trat bei der DLL-Initialisierung ein Fehler auf.  
  
## <a name="resolution"></a>Auflösung  
 Analysieren Sie den Code der `DllMain`-Funktion für die fehlgeschlagene DLL, und identifizieren Sie die Ursache des Initialisierungsfehlers.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR. Es werden nur Daten zum Rückgabewert für `DllMain` gemeldet.  
  
## <a name="output"></a>Output  
 Eine Meldung, die anzeigt, dass eine mit der Ursache DLL_PROCESS_ATTACH aufgerufene `DllMain`-Funktion FALSE zurückgegeben hat. Beachten Sie, dass dieser MDA nur aktiviert wird, wenn `DllMain` in verwalteten Code implementiert wird.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
