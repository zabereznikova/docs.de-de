---
title: Kopieren und Fixieren
description: Erfahren Sie, wie der Interop-Marshaller Daten kopieren oder fixieren kann, die gerade gemarshallt werden. Beim Kopieren von Daten wird eine Kopie der Daten aus einem Speicherort an einem anderen abgelegt.
ms.date: 03/30/2017
helpviewer_keywords:
- pinning, interop marshaling
- copying, interop marshaling
- interop marshaling, copying
- interop marshaling, pinning
ms.assetid: 0059f576-e460-4e70-b257-668870e420b8
ms.openlocfilehash: b7931813cd5254375eda81515f388c85c78fa284
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618778"
---
# <a name="copying-and-pinning"></a>Kopieren und Fixieren

Beim Marshalling von Daten kann der Interop-Marshaller die gemarshallten Daten kopieren oder fixieren. Beim Kopieren der Daten wird eine Kopie der Daten aus einem Speicherort an einem anderen Speicherort abgelegt. Die folgende Abbildung veranschaulicht die Unterschiede zwischen dem Kopieren eines Werttyps und dem Kopieren eines Typs, der als Verweis von einem verwalteten Speicher zu einem nicht verwalteten Speicher übergeben wird.

![Diagramm, das zeigt, wie Wert- und Verweistypen kopiert werden.](./media/copying-and-pinning/interop-marshal-copy.gif)

Als Wert übergebene Methodenargumente werden in einen nicht verwalteten Code als Werte im Stapel gemarshallt. Der Kopiervorgang wird direkt ausgeführt. Als Verweis übergebene Argumente werden als Zeiger im Stapel übergeben. Auch Verweistypen werden als Wert und als Verweis übergebenen. Die folgende Abbildung zeigt, dass als Wert übergebene Verweistypen entweder kopiert oder fixiert werden:

![Diagramm mit Verweistypen, die nach Wert und Verweis übergeben werden.](./media/copying-and-pinning/interop-marshal-reference-pin.gif)

Beim Fixieren werden die Daten vorübergehend an ihrem aktuellen Speicherort gesperrt. Dadurch können sie nicht vom Garbage Collector der Common Language Runtime verschoben werden. Der Marshaller fixiert die Daten, um den Aufwand beim Kopieren zu reduzieren und die Leistung zu verbessern. Ob Daten während des Marshallingvorgangs kopiert oder fixiert werden, wird durch den Datentyp bestimmt.  Beim Marshalling für Objekte, wie z.B. <xref:System.String>, werden die Daten automatisch fixiert. Sie können jedoch mithilfe der <xref:System.Runtime.InteropServices.GCHandle>-Klasse den Speicher auch manuell fixieren.

## <a name="formatted-blittable-classes"></a>Formatierte blitfähige Klassen

Formatierte [blitfähige](blittable-and-non-blittable-types.md) Klassen verfügen über ein festes Layout (formatiert) und eine allgemeine Darstellung der Daten im verwalteten und im nicht verwalteten Speicher. Wenn diese Typen gemarshallt werden müssen, wird ein Zeiger auf das Objekt im Heap direkt an den Aufgerufenen übergeben. Der Aufgerufene kann den Inhalt des Speicherorts ändern, auf den der Zeiger verweist.

> [!NOTE]
> Der Aufgerufene kann den Speicherinhalt ändern, wenn der Parameter als Ausgabe- oder Ein-/Ausgabeparameter markiert ist. Im Gegensatz dazu sollte der Aufgerufene den Inhalt nicht ändern, wenn der Parameter zum Marshallen als Eingabeparameter festgelegt ist. Dies ist die Standardeinstellung für formatierte blitfähige Typen. Das Ändern von Eingabeobjekten kann zu Problemen führen, wenn die gleiche Klasse in eine Typbibliothek exportiert und auch für apartmentübergreifende Aufrufe verwendet wird.

## <a name="formatted-non-blittable-classes"></a>Formatierte nicht blitfähige Klassen

Formatierte [nicht blitfähige](blittable-and-non-blittable-types.md) Klassen verfügen über ein festes Layout (formatiert), doch die Daten werden im verwalteten und im nicht verwalteten Speicher unterschiedlich dargestellt. Unter den folgenden Bedingungen kann eine Umwandlung der Daten erforderlich sein:

- Wenn eine nicht blitfähige Klasse als Wert gemarshallt wird, erhält der Aufgerufene einen Zeiger auf eine Kopie der Datenstruktur.

- Wenn eine nicht blitfähige Klasse als Verweis gemarshallt wird, erhält der Aufgerufene einen Zeiger auf einen Zeiger auf eine Kopie der Datenstruktur.

- Wenn das <xref:System.Runtime.InteropServices.InAttribute>-Attribut festgelegt ist, wird diese Kopie immer mit dem Zustand der Instanz initialisiert. Das Marshalling erfolgt nach Bedarf.

- Wenn das <xref:System.Runtime.InteropServices.OutAttribute>-Attribut festgelegt ist, wird der Zustand bei der Rückgabe immer zurück in die Instanz kopiert. Das Marshalling erfolgt nach Bedarf.

- Wenn sowohl **InAttribute** als auch **OutAttribute** festgelegt sind, werden beide Kopien benötigt. Wenn kein Attribut verwendet wird, kann der Marshaller durch Beseitigen beider Kopien eine Optimierung vornehmen.

## <a name="reference-types"></a>Verweistypen

Verweistypen können als Wert oder als Verweis übergeben werden. Werden sie als Wert übergeben, wird ein Zeiger auf den Typ im Stapel übergeben. Werden sie als Verweis übergeben, wird ein Zeiger auf einen Zeiger auf den Typ im Stapel übergeben.

Verweistypen weisen das folgende bedingte Verhalten auf:

- Wird ein Verweistyp als Wert übergeben, und verfügt er über Member nicht blitfähiger Typen, werden die Typen zweimal konvertiert:

  - bei der Übergabe eines Arguments an die nicht verwaltete Seite

  - bei der Rückgabe aus dem Aufruf

  Diese Typen werden als Eingabeparameter gemarshallt, um unnötiges Kopieren und Konvertieren zu vermeiden. Damit der Aufrufer die durch den Aufgerufenen vorgenommenen Änderungen sehen kann, müssen Sie die Attribute **InAttribute** und **OutAttribute** explizit auf ein Argument anwenden.

- Wird ein Verweistyp als Wert übergeben, und verfügt er nur über Member blitfähiger Typen, kann er während des Marshallings fixiert werden. Alle vom Aufgerufenen an den Membern des Typs vorgenommen Änderungen sind für den Aufrufer sichtbar. Wenn Sie dieses Verhalten wünschen, wenden Sie die Attribute **InAttribute** und **OutAttribute** explizit an. Ohne diese direktionalen Attribute werden keine direktionalen Informationen vom Interop-Marshaller in die Typbibliothek exportiert (der Export erfolgt standardmäßig als Eingabeparameter). Dies kann zu Problemen beim apartmentübergreifenden COM-Marshalling führen.

- Wird ein Verweistyp als Verweis übergeben, wird er standardmäßig als Ein-/Ausgabeparameter gemarshallt.

## <a name="systemstring-and-systemtextstringbuilder"></a>System.String und System.Text.StringBuilder

Wenn Daten als Wert oder als Verweis in einen nicht verwalteten Code gemarshallt werden, kopiert der Marshaller die Daten in der Regel in einen sekundären Puffer (wobei Zeichensätze während des Kopiervorgangs eventuell konvertiert werden) und übergibt an den Aufgerufenen einen Verweis auf den Puffer. Der Verweis wird immer mit **CoTaskMemAlloc** zugeordnet. Außer es handelt sich um ein **BSTR**, das mit **SysAllocString** zugeordnet wird.

Wenn beide Zeichenfolgentypen als Wert gemarshallt werden (wie etwa bei einer Unicode-Zeichenfolge), übergibt der Marshaller dem Aufgerufenen einen direkten Zeiger auf die verwalteten Zeichenfolgen im internen Unicode-Puffer, anstatt sie in einen neuen Puffer zu kopieren.

> [!CAUTION]
> Wird eine Zeichenfolge als Wert übergeben, darf der Aufgerufene den vom Marshaller übergebenen Verweis nie ändern. Andernfalls kann der verwaltete Heap beschädigt werden.

Wenn ein <xref:System.String?displayProperty=nameWithType> als Verweis übergeben wird, kopiert der Marshaller den Inhalt der Zeichenfolge vor dem Aufruf in einen sekundären Puffer. Anschließend kopiert er den Inhalt des Puffers bei der Rückgabe aus dem Aufruf in eine neue Zeichenfolge. So wird sichergestellt, dass die unveränderliche verwaltete Zeichenfolge unverändert bleibt.

Wenn ein <xref:System.Text.StringBuilder?displayProperty=nameWithType> als Wert übergeben wird, übergibt der Marshaller dem Aufrufer direkt einen Verweis auf den internen Puffer von **StringBuilder**. Aufrufer und Aufgerufener müssen bei der Größe des Puffers übereinstimmen. Der Aufrufer ist für das Erstellen von **StringBuilder** in einer angemessenen Länge zuständig. Der Aufgerufene muss die erforderlichen Vorsichtsmaßnahmen treffen, um einen Pufferüberlauf zu verhindern. **StringBuilder** stellt eine Ausnahme zu der Regel dar, dass als Wert übergebene Verweistypen standardmäßig als Eingabeparameter übergeben werden. Es wird immer als Ein-/Ausgabeparameter übergeben.

## <a name="see-also"></a>Siehe auch

- [Default Marshaling Behavior (Standardmäßiges Marshallingverhalten)](default-marshaling-behavior.md)
- [Direktionale Attribute](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))
- [Interop Marshaling (Interop-Marshalling)](interop-marshaling.md)
