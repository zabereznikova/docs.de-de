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
ms.openlocfilehash: 9ca39d989cc7bc16ec2678ba5fa53710899f3ac4
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107157"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a>Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource

Bei einer Zeit Zonen fähigen Anwendung ist es häufig erforderlich, dass eine bestimmte Zeitzone vorhanden ist. Da die Verfügbarkeit einzelner <xref:System.TimeZoneInfo> Objekte jedoch von Informationen abhängig ist, die in der Registrierung des lokalen Systems gespeichert sind, sind möglicherweise auch für die Kunden verfügbare Zeitzonen nicht vorhanden. Außerdem werden Informationen über benutzerdefinierte Zeitzonen, die mithilfe der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> -Methode instanziiert werden, nicht mit anderen Zeitzoneninformationen in der Registrierung gespeichert. Um sicherzustellen, dass diese Zeitzonen bei Bedarf verfügbar sind, können Sie Sie durch serialisieren speichern und später wiederherstellen, indem Sie Sie deserialisieren.

In der Regel erfolgt die <xref:System.TimeZoneInfo> Serialisierung eines-Objekts von der Zeit Zonen fähigen Anwendung. Abhängig vom Datenspeicher, der für serialisierte <xref:System.TimeZoneInfo> Objekte verwendet wird, werden Zeit Zonendaten möglicherweise als Teil einer Setup-oder Installationsroutine (z. b. wenn die Daten in einem Anwendungs Schlüssel der Registrierung gespeichert sind) oder als Teil einer hilfsprogrammroutine, die ausführt, serialisiert. vor der Kompilierung der endgültigen Anwendung (z. b. wenn die serialisierten Daten in einer .NET-XML-Ressourcen Datei (. resx) gespeichert sind).

Zusätzlich zu einer Ressourcen Datei, die mit der Anwendung kompiliert wird, können auch mehrere andere Datenspeicher für Zeitzoneninformationen verwendet werden. Hierzu gehört Folgendes:

- Die Registrierung. Beachten Sie, dass eine Anwendung die untergeordneten Schlüssel Ihres eigenen Anwendungs Schlüssels verwenden sollte, um benutzerdefinierte Zeit Zonendaten zu speichern, anstatt die Unterschlüssel von HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows nt\currentversion\zeitzonen zu verwenden.

- Konfigurationsdateien.

- Andere Systemdateien.

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a>So speichern Sie eine Zeitzone durch Serialisierung in eine RESX-Datei

1. Rufen Sie eine vorhandene Zeitzone ab, oder erstellen Sie eine neue Zeitzone.

   Weitere Informationen zum Abrufen einer vorhandenen Zeitzone finden [Sie unter Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeit](../../../docs/standard/datetime/access-utc-and-local.md) Zonen [Objekte und Gewusst wie: Instanziieren Sie ein TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md)-Objekt.

   Um eine neue Zeitzone zu erstellen, rufen Sie eine der über Ladungen der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> -Methode auf. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) und [Gewusst wie: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).

2. Rufen Sie <xref:System.TimeZoneInfo.ToSerializedString%2A> die-Methode auf, um eine Zeichenfolge zu erstellen, die die Daten der Zeitzone enthält.

3. Instanziieren Sie <xref:System.IO.StreamWriter> ein-Objekt, indem Sie den Namen und optional den Pfad der RESX-Datei <xref:System.IO.StreamWriter> dem-Klassenkonstruktor bereitstellen.

4. Instanziieren Sie <xref:System.Resources.ResXResourceWriter> ein-Objekt, <xref:System.IO.StreamWriter> indem Sie das <xref:System.Resources.ResXResourceWriter> -Objekt an den-Klassenkonstruktor übergeben.

5. Übergeben Sie die serialisierte Zeichenfolge der Zeitzone an <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> die-Methode.

6. Rufen Sie die <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>-Methode auf.

7. Rufen Sie die <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>-Methode auf.

8. Schließen Sie <xref:System.IO.StreamWriter> das Objekt, indem <xref:System.IO.StreamWriter.Close%2A> Sie seine-Methode aufrufen.

9. Fügen Sie die generierte RESX-Datei zum Visual Studio-Projekt der Anwendung hinzu.

10. Stellen Sie mithilfe des Fensters **Eigenschaften** in Visual Studio sicher, dass die Eigenschaft Buildvorgang der Datei ". resx" auf **eingebettete Ressource**festgelegt ist.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein <xref:System.TimeZoneInfo> -Objekt, das die Central Standard Time darstellt, und ein <xref:System.TimeZoneInfo> -Objekt, das die Palmer Station darstellt, in der Antarktis-Zeit in eine .NET-XML-Ressourcen Datei mit dem Namen SerializedTimeZones. resx serialisiert. Central Standard Time wird normalerweise in der Registrierung definiert. Palmer Station, Antarktis ist eine benutzerdefinierte Zeitzone.

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

In diesem Beispiel werden <xref:System.TimeZoneInfo> -Objekte so serialisiert, dass Sie zum Zeitpunkt der Kompilierung in einer Ressourcen Datei verfügbar sind.

Da die <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> -Methode einer .NET-XML-Ressourcen Datei umfassende Header Informationen hinzufügt, kann Sie nicht zum Hinzufügen von Ressourcen zu einer vorhandenen Datei verwendet werden. Im Beispiel wird dies behandelt, indem die Datei "SerializedTimeZones. resx" überprüft und, falls vorhanden, alle anderen Ressourcen als die beiden serialisierten Zeitzonen in einem generischen <xref:System.Collections.Generic.Dictionary%602> Objekt gespeichert werden. Die vorhandene Datei wird dann gelöscht, und die vorhandenen Ressourcen werden der neuen Datei "SerializedTimeZones. resx" hinzugefügt. Die serialisierten Zeit Zonendaten werden dieser Datei ebenfalls hinzugefügt.

Die Schlüsselfelder (oder **Namen**) der Ressourcen dürfen keine eingebetteten Leerzeichen enthalten. Die <xref:System.String.Replace%28System.String%2CSystem.String%29> -Methode wird aufgerufen, um alle eingebetteten Leerzeichen in den Zeit Zonen bezeichgern zu entfernen, bevor Sie der Ressourcen Datei zugewiesen werden.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

- Dem Projekt wird ein Verweis auf "System. Windows. Forms. dll" und "System. Core. dll" hinzugefügt.

- Die folgenden Namespaces werden importiert:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
- [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)
- [Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
