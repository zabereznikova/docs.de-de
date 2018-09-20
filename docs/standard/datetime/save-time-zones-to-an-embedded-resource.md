---
title: 'Gewusst wie: Speichern von Zeitzonen in einer eingebetteten Ressource'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], saving
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 921874e774d18751c29db495dac1bc53d10cc8ad
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "44778628"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a>Gewusst wie: Speichern von Zeitzonen in einer eingebetteten Ressource

Eine Zeitzonen unterstützende Anwendung häufig erfordert das Vorhandensein einer bestimmten Zeitzone. Aber da die Verfügbarkeit der einzelnen <xref:System.TimeZoneInfo> -Objekten hängt von Informationen, die in der Registrierung des lokalen Systems gespeichert, normalerweise auch vorhandene Zeitzonen ist ggf. nicht vorhanden. Darüber hinaus Informationen über benutzerdefinierte Zeitzonen instanziiert werden, indem die <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode ist nicht mit anderen Informationen zur Zeitzone, in der Registrierung gespeichert. Um sicherzustellen, dass diese Zeitzonen verfügbar sind, wenn sie benötigt werden, können Sie speichern, indem sie serialisieren und diese später wiederherstellen, indem sie deserialisieren.

Serialisierung in der Regel eine <xref:System.TimeZoneInfo> Objekt tritt auf, abgesehen von der Zeitzonen unterstützende Anwendung. Je nach Datenspeicher verwendet, um serialisierte aufzunehmen <xref:System.TimeZoneInfo> Objekten, die Zeitzonendaten serialisiert werden können, als Teil einer Routine Einrichtung oder Installation (z. B., wenn die Daten in einen Anwendungsschlüssel, der Registrierung gespeichert ist) oder als Teil einer Hilfsprogramm-Routine, die ausgeführt wird bevor die endgültige Anwendung kompiliert wird, (z. B. wenn die serialisierten Daten in einer .NET XML-Ressourcendatei (RESX) gespeichert werden).

Zusätzlich zu einer Ressourcendatei, die mit der Anwendung kompiliert wird, können mehrere andere Datenspeicher für Informationen zur Zeitzone verwendet werden. Hierzu gehört Folgendes:

* Die Registrierung. Beachten Sie, dass eine Anwendung die Unterschlüssel des eigenen Anwendungsschlüssel verwenden sollte, zum Speichern von Daten benutzerdefinierte Zeitzonen, anstatt die Unterschlüssel des HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones verzeichnet sind.

* Konfigurationsdateien.

* Andere Systemdateien.

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a>Um eine Zeitzone durch eine Serialisierung in einer RESX-Datei zu speichern.

1. Rufen Sie eine vorhandene Zeitzone aus, oder erstellen Sie eine neue Zeitzone.

   Um eine vorhandene Zeitzone abzurufen, finden Sie unter [Vorgehensweise: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte](../../../docs/standard/datetime/access-utc-and-local.md) und [wie: instanziieren ein TimeZoneInfo-Objekts](../../../docs/standard/datetime/instantiate-time-zone-info.md).

   Um eine neue Zeitzone zu erstellen, rufen Sie eine der Überladungen der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) und [Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).

2. Rufen Sie die <xref:System.TimeZoneInfo.ToSerializedString%2A> Methode, um eine Zeichenfolge zu erstellen, die Daten von der Standardzeit der Zeitzone enthält.

3. Instanziieren einer <xref:System.IO.StreamWriter> Objekts. Hierbei geben den Namen und optional den Pfad der RESX-Datei, die die <xref:System.IO.StreamWriter> Klassenkonstruktor.

4. Instanziieren einer <xref:System.Resources.ResXResourceWriter> -Objekts durch Übergeben der <xref:System.IO.StreamWriter> -Objekt an die <xref:System.Resources.ResXResourceWriter> Klassenkonstruktor.

5. Übergeben der Zeitzone serialisierte Zeichenfolge an die <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> Methode.

6. Rufen Sie die <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>-Methode auf.

7. Rufen Sie die <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>-Methode auf.

8. Schließen der <xref:System.IO.StreamWriter> -Objekt durch Aufrufen der <xref:System.IO.StreamWriter.Close%2A> Methode.

9. Fügen Sie die generierte RESX-Datei der Anwendung Visual Studio-Projekt hinzu.

10. Mithilfe der **Eigenschaften** Fenster in Visual Studio verwenden, stellen sicher, dass der RESX-Datei **Buildvorgang** -Eigenschaftensatz auf **eingebettete Ressource**.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine <xref:System.TimeZoneInfo> Objekt, das Central Standard Time darstellt und einen <xref:System.TimeZoneInfo> -Objekt, das die Palmer-Station Zeitzone Antarktis in eine .NET XML-Ressourcendatei darstellt, die mit dem Namen SerializedTimeZones.resx. Central Normalzeit wird in der Regel in der Registrierung definiert. Palmer-Station, Antarktis ist eine benutzerdefinierte Zeitzone.

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

In diesem Beispiel serialisiert <xref:System.TimeZoneInfo> Objekten, die sie zum Zeitpunkt der Kompilierung in einer Ressourcendatei verfügbar sind.

Da die <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> Methode fügt die vollständige Kopfzeile in eine .NET XML-Ressourcendatei, es kann nicht verwendet werden, um Ressourcen zu einer vorhandenen Datei hinzufügen. Im Beispiel verarbeitet dies durch die Datei SerializedTimeZones.resx gesucht, und wenn es vorhanden ist, Speichern aller zugehörigen Ressourcen nicht die beiden serialisierten Zeitzonen in einer generischen <xref:System.Collections.Generic.Dictionary%602> Objekt. Die vorhandene Datei wird dann gelöscht, und die vorhandenen Ressourcen werden in eine neue SerializedTimeZones.resx-Datei hinzugefügt. Diese Datei werden auch die serialisierte Zeitzonendaten hinzugefügt.

Der Schlüssel (oder **Namen**) von Ressourcen sollte keine eingebetteten Leerzeichen enthalten. Die <xref:System.String.Replace%28System.String%2CSystem.String%29> Methode wird aufgerufen, um sämtliche eingebettete Leerzeichen in der Zeitzonenbezeichner zu entfernen, bevor sie die Ressourcendatei zugewiesen sind.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

* Dass das Projekt ein Verweis auf "System.Windows.Forms.dll" und "System.Core.dll" hinzugefügt werden.

* Dass die folgenden Namespaces importiert werden:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Siehe auch

* [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
* [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)
* [Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
