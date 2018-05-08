---
title: 'Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource'
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
ms.openlocfilehash: 4dd7e6db78b76d737cb4646c2fad79d96fb60aee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a>Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource

Häufig eine Zeitzone-fähige Anwendung erfordert das Vorhandensein einer bestimmten Zeitzone. Jedoch, da die Verfügbarkeit einzelner <xref:System.TimeZoneInfo> -Objekten hängt von Informationen, die in der Registrierung des lokalen Systems gespeichert, selbst normalerweise verfügbaren Zeitzonen möglicherweise nicht vorhanden. Darüber hinaus Informationen über benutzerdefinierte Zeitzonen instanziiert, indem die <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode ist nicht mit anderen Informationen zur Zeitzone in der Registrierung gespeichert. Um sicherzustellen, dass diese Zeitzonen verfügbar sind, wenn sie benötigt werden, können Sie speichern, indem sie serialisieren und diese später wiederherstellen, indem sie deserialisieren.

In der Regel Serialisieren einer <xref:System.TimeZoneInfo> Objekt tritt auf, abgesehen von der Zeitzone-fähigen Anwendung. Abhängig von der Datenspeicher verwendet, um serialisierte halten <xref:System.TimeZoneInfo> Objekte Zeitzonendaten serialisiert werden können, im Rahmen einer Routine Einrichtung oder Installation (z. B., wenn die Daten in einen Anwendungsschlüssel der Registrierung gespeichert ist) oder als Teil einer Hilfsprogramm-Routine, die ausgeführt wird vor der endgültige Anwendung kompiliert wird, (z. B. wenn die serialisierten Daten in einer .NET XML-Ressourcendatei (.resx) gespeichert ist).

Zusätzlich zu einer Ressourcendatei, die mit der Anwendung kompiliert wird, können andere Datenspeicher für die Zeitzoneninformationen verwendet werden. Hierzu gehört Folgendes:

* Die Registrierung. Beachten Sie, dass eine Anwendung der Unterschlüssel des Anwendungsschlüssel seines eigenen verwenden soll, um benutzerdefinierte Zeitzonendaten, anstatt die Unterschlüssel HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zonen zu speichern.

* Konfigurationsdateien.

* Andere Systemdateien.

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a>Um eine Zeitzone durch eine Serialisierung in eine RESX-Datei zu speichern.

1. Abzurufen Sie eine vorhandene Zeitzone, oder erstellen Sie eine neue Zeitzone.

   Um eine vorhandene Zeitzone abzurufen, finden Sie unter [Vorgehensweise: Zugreifen auf die vordefinierte UTC und Ortszeit Zonenobjekte](../../../docs/standard/datetime/access-utc-and-local.md) und [wie: Instanziieren eines TimeZoneInfo-Objekts](../../../docs/standard/datetime/instantiate-time-zone-info.md).

   Um eine neue Zeitzone zu erstellen, rufen Sie eine der Überladungen der der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) und [Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).

2. Rufen Sie die <xref:System.TimeZoneInfo.ToSerializedString%2A> Methode, um eine Zeichenfolge zu erstellen, das die Zeitzone Daten enthält.

3. Instanziieren einer <xref:System.IO.StreamWriter> Objekt, indem Sie den Namen und optional den Pfad der RESX-Datei, die die <xref:System.IO.StreamWriter> Klassenkonstruktor.

4. Instanziieren einer <xref:System.Resources.ResXResourceWriter> -Objekt durch Übergeben der <xref:System.IO.StreamWriter> -Objekt an die <xref:System.Resources.ResXResourceWriter> Klassenkonstruktor.

5. Übergeben der Zeitzone serialisierte Zeichenfolge an die <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> Methode.

6. Rufen Sie die <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>-Methode auf.

7. Rufen Sie die <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>-Methode auf.

8. Schließen der <xref:System.IO.StreamWriter> Objekt durch Aufrufen seiner <xref:System.IO.StreamWriter.Close%2A> Methode.

9. Die Anwendung von Visual Studio-Projekt die generierte RESX-Datei hinzugefügt.

10. Mithilfe der **Eigenschaften** Fenster in Visual Studio verwenden, stellen sicher, dass der RESX-Datei **Buildvorgang** -Eigenschaftensatz auf **eingebettete Ressource**.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine <xref:System.TimeZoneInfo> Objekt, das Central Normalzeit darstellt und ein <xref:System.TimeZoneInfo> Objekt, das zu einer .NET XML-Ressourcendatei mit dem Namen SerializedTimeZones.resx der Palmer Station, Antarktis Zeit darstellt. Central Normalzeit ist in der Regel in der Registrierung definiert. Palmer Station, Antarktis ist eine benutzerdefinierte Zeitzone.

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

In diesem Beispiel serialisiert <xref:System.TimeZoneInfo> -Objekten, die sie zum Zeitpunkt der Kompilierung in einer Ressourcendatei verfügbar sind.

Da die <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> Methode fügt vollständige Header-Informationen zu einer .NET XML-Ressourcendatei, die nicht zum Hinzufügen von Ressourcen zu einer vorhandenen Datei verwendet werden. Im Beispiel mit der Überprüfung der Datei SerializedTimeZones.resx behandelt und, falls vorhanden, speichern alle Ressourcen außer die beiden serialisiert Zeitzonen auf einen allgemeinen <xref:System.Collections.Generic.Dictionary%602> Objekt. Die vorhandene Datei wird dann gelöscht, und vorhandenen Ressourcen werden in eine neue SerializedTimeZones.resx-Datei hinzugefügt. Diese Datei werden auch der serialisierten Zeitzonendaten hinzugefügt.

Der Schlüssel (oder **Namen**) von Ressourcen sollten keine eingebettete Leerzeichen enthalten. Die <xref:System.String.Replace%28System.String%2CSystem.String%29> Methode wird aufgerufen, um alle eingebetteten Leerzeichen in der Zeitzonenbezeichner zu entfernen, bevor sie die Ressourcendatei zugewiesen werden.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

* Dem Projekt ein Verweis auf System.Windows.Forms.dll und "System.Core.dll" hinzugefügt werden.

* Dass die folgenden Namespaces importiert werden:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
[Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)
[Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
