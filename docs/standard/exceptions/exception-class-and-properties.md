---
title: Exception-Klasse und Exception-Eigenschaften
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, Exception class
- Exception class
ms.assetid: e2e1f8c4-e7b4-467d-9a66-13c90861221d
ms.openlocfilehash: df05150a5bdd5d24766be252f5cec9a436720d8c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "75708944"
---
# <a name="exception-class-and-properties"></a>Ausnahmeklasse und -eigenschaften

Die <xref:System.Exception>-Klasse ist die Basisklasse, von der Ausnahmen erben. Die Hierarchie der <xref:System.InvalidCastException>-Klasse sieht beispielsweise wie folgt aus:

<xref:System.Object>\
&nbsp;&nbsp;<xref:System.Exception>\
&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.SystemException>\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.InvalidCastException>

Die <xref:System.Exception>-Klasse verfügt über die folgenden Eigenschaften, die das Verständnis einer Ausnahme erleichtern.

| Eigenschaftenname | Beschreibung |
| ------------- | ----------- |
| <xref:System.Exception.Data> | Ein <xref:System.Collections.IDictionary>, das beliebige Daten in Schlüssel-Wert-Paaren enthält. |
| <xref:System.Exception.HelpLink> | Kann einen URL (oder URN) zu einer Hilfedatei enthalten, die ausführliche Informationen zur Ursache einer Ausnahme bereitstellt. |
| <xref:System.Exception.InnerException> | Diese Eigenschaft kann verwendet werden, um während der Ausnahmebehandlung eine Reihe von Ausnahmen zu erstellen und beizubehalten. Sie können sie verwenden, um eine neue Ausnahme zu erstellen, die zuvor bereits abgefangene Ausnahmen enthält. Die ursprüngliche Ausnahme kann durch die zweite Ausnahme in der <xref:System.Exception.InnerException>-Eigenschaft abgefangen werden. So kann der Code, der die zweite Ausnahme verarbeitet, die zusätzlichen Informationen untersuchen. Ein Beispiel: Sie verfügen über eine Methode, die ein unzureichend formatiertes Argument erhält.  Der Code versucht, das Argument zu lesen, es wird aber eine Ausnahme ausgelöst. Die Methode fängt die Ausnahme ab und löst eine <xref:System.FormatException> aus. Um die Fähigkeit des Aufrufers zu erhöhen, den Grund für eine Ausnahme zu ermitteln, ist es manchmal wünschenswert, dass eine Methode eine von einer Hilfsroutine ausgelöste Ausnahme abfängt und dann eine Ausnahme auslöst, die bessere Hinweise auf den aufgetretenen Fehler bietet. Es kann eine neue, aussagekräftigere Ausnahme erstellt werden, in der der Verweis auf die innere Ausnahme auf die ursprüngliche Ausnahme festgelegt werden kann. Diese aussagekräftigere Ausnahme kann für den Aufrufer ausgelöst werden. Beachten Sie, dass Sie mit dieser Funktionalität eine Reihe von verknüpften Ausnahmen erstellen können, die mit der Ausnahme endet, die zuerst ausgelöst wurde. |
| <xref:System.Exception.Message> | Bietet Informationen zur Ursache einer Ausnahme.
| <xref:System.Exception.Source> | Gibt den Namen der Anwendung oder des Objekts zurück, die bzw. das den Fehler verursacht hat, oder legt diesen fest. |
| <xref:System.Exception.StackTrace>| Enthält eine Stapelüberwachung, die verwendet kann, um zu ermitteln, wo ein Fehler aufgetreten ist. Die Stapelüberwachung beinhaltet den Quelldateinamen und die Programmzeilennummer, falls Debuginformationen verfügbar sind. |

Die meisten der Klassen, die von <xref:System.Exception> erben, implementieren keine weiteren Member und stellen keine weitere Funktionalität bereit. Sie erben einfach von <xref:System.Exception>. Daher finden sich die wichtigsten Informationen für eine Ausnahme in der Hierarchie der Ausnahmeklassen, dem Namen der Ausnahme und den in der Ausnahme enthaltenen Details.

Es wird empfohlen, nur Objekte auszulösen und abzufangen, die von <xref:System.Exception> abgeleitet sind. Sie können jedoch jedes beliebige, von der <xref:System.Object>-Klasse abgeleitete Objekt als Ausnahme auslösen. Beachten Sie, dass einige Sprachen nur das Auslösen und Abfangen von Objekten unterstützen, die nicht von <xref:System.Exception> abgeleitet sind.
  
## <a name="see-also"></a>Weitere Informationen

- [Ausnahmen](index.md)
