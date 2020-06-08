---
title: 'Gewusst wie: Implementieren eines Wartevorgangs mit zwei Phasen mit SpinWait'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
ms.openlocfilehash: 4b2bc79a7b652c34334d5a78d9c9af328993ff44
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84279205"
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a>Gewusst wie: Implementieren eines Wartevorgangs mit zwei Phasen mit SpinWait
Das folgende Beispiel zeigt, wie Sie mit einem <xref:System.Threading.SpinWait?displayProperty=nameWithType>-Objekt einen zweiphasigen Wartevorgang implementieren. In der ersten Phase rotiert das Synchronisierungsobjekt, ein `Latch`, für einige Zyklen und überprüft dabei, ob die Sperre verfügbar geworden ist. Wenn in der zweiten Phase die Sperre verfügbar wird, erfolgt die Rückgabe der `Wait`-Methode ohne Verwendung von <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> zur Ausführung des Wartevorgangs; andernfalls führt `Wait` den Wartevorgang aus.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt eine sehr grundlegende Implementierung einer Latchsynchronisierungsprimitiven. Sie können diese Datenstruktur verwenden, wenn die Wartezeiten voraussichtlich sehr kurz sind. Das Beispiel dient nur der Veranschaulichung. Wenn Sie in Ihrem Programm Latchfunktionalität benötigen, erwägen Sie die Verwendung von <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 Der Latch verwendet das <xref:System.Threading.SpinWait>-Objekt für Schleifendurchläufe, bis der nächste Aufruf von `SpinOnce` veranlasst, dass <xref:System.Threading.SpinWait> das Zeitsegment des Threads bereitstellt. An diesem Punkt bewirkt der Latch seinen eigenen Kontextwechsel durch Aufruf von <xref:System.Threading.WaitHandle.WaitOne%2A> in <xref:System.Threading.ManualResetEvent> und Übergabe des Rests des Timeoutwerts.  
  
 Die Protokollausgabe zeigt, wie oft der Latch die Leistung durch Aktivieren der Sperre ohne Verwendung von <xref:System.Threading.ManualResetEvent> erhöhen konnte.  
  
## <a name="see-also"></a>Weitere Informationen

- [SpinWait](spinwait.md)
- [Threading Objects and Features (Threadingobjekte und -funktionen)](threading-objects-and-features.md)
