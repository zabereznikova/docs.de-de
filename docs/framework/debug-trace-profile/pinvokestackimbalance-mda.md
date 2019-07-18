---
title: pInvokeStackImbalance-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- stack depth
- platform invoke stack imbalance
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- PInvokeStackImbalance MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: 34ddc6bd-1675-4f35-86aa-de1645d5c631
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9ecdfd708217f260b0c02383159fab88948029c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61874210"
---
# <a name="pinvokestackimbalance-mda"></a>PInvokeStackImbalance-MDA

Die `PInvokeStackImbalance` -Assistent für verwaltetes Debuggens (MDA) wird aktiviert, wenn die CLR erkennt, dass die Stapeltiefe nach einem Plattformaufruf nicht mit der Stapeltiefe, der angegebenen Aufrufkonvention entspricht der <xref:System.Runtime.InteropServices.DllImportAttribute> Attribut und die die Deklaration der Parameter in der verwalteten Signatur.

Der `PInvokeStackImbalance`-MDA wird nur für 32-Bit-x86-Plattformen implementiert.

> [!NOTE]
> Die `PInvokeStackImbalance` MDA ist standardmäßig deaktiviert. In Visual Studio 2017 die `PInvokeStackImbalance` MDA wird angezeigt, der **Managed Debugging Assistants** Liste der **Ausnahmeeinstellungen** Dialogfeld (wird angezeigt, wenn Sie auswählen, **Debuggen**  >  **Windows** > **Ausnahmeeinstellungen**). Allerdings aktivieren bzw. Deaktivieren der **unterbrechen Wenn ausgelöst** das Kontrollkästchen nicht aktivieren oder deaktivieren Sie den MDA; Hierdurch wird nur festgelegt, ob es sich bei Visual Studio eine Ausnahme auslöst, wenn der MDA aktiviert wird.

## <a name="symptoms"></a>Symptome

Während eines Plattformaufrufs in einer Anwendung oder danach kommt es zu einer Zugriffsverletzung oder Speicherbeschädigung.

## <a name="cause"></a>Ursache

Die verwaltete Signatur des Plattformaufrufs stimmt möglicherweise nicht mit der nicht verwalteten Signatur der aufgerufenen Methode überein.  Dazu kann es kommen, wenn für die verwaltete Methode nicht die korrekte Anzahl der Parameter bzw. eine falsche Parametergröße deklariert wurde.  Der MDA wird auch aktiviert, wenn die ggf. durch das <xref:System.Runtime.InteropServices.DllImportAttribute>-Attribut festgelegte Aufrufkonvention nicht mit der nicht verwalteten Aufrufkonvention übereinstimmt.

## <a name="resolution"></a>Auflösung

Überprüfen Sie die Signatur des verwalteten Plattformaufrufs sowie die Aufrufkonvention, um sich zu vergewissern, dass diese mit der Signatur und Aufrufkonvention des systemeigenen Ziels übereinstimmen.  Versuchen Sie, die Aufrufkonvention sowohl auf der verwalteten als auch auf der nicht verwalteten Seite explizit anzugeben. Es ist ebenfalls möglich (wenn auch weniger wahrscheinlich), dass die nicht verwaltete Funktion aus einem anderen Grund einen nicht ausgeglichenen Stapel verursacht hat, beispielsweise durch einen Programmfehler im nicht verwalteten Compiler.

## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit

Erzwingt für alle Plattformaufrufe die Verwendung des nicht optimierten Pfads in die CLR.

## <a name="output"></a>Output

Die MDA-Meldung enthält den Namen der Plattformaufrufmethode, die das Stapelungleichgewicht verursacht hat. Beispielmeldung eines Plattformaufrufs der `SampleMethod`-Methode: 

**Ein Aufruf PInvoke-Funktion "SampleMethod" hat einen nicht ausgeglichenen Stapel. Dies ist wahrscheinlich, weil die verwaltete PInvoke-Signatur nicht die Signatur nicht verwaltetes Ziel übereinstimmt. Überprüfen Sie, dass die Aufrufkonvention und die Parameter von PInvoke-Signatur die nicht verwalteten Ziel-Signatur entsprechen.**

## <a name="configuration"></a>Konfiguration

```xml
<mdaConfig>
  <assistants>
    <pInvokeStackImbalance />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Interop Marshaling (Interop-Marshalling)](../../../docs/framework/interop/interop-marshaling.md)
