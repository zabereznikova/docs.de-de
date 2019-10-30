---
title: 'Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
ms.openlocfilehash: cd2119d6d22f3f676b7167ed545aeb058123cfb5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122193"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a>Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource

In diesem Thema wird beschrieben, wie Zeitzonen wieder hergestellt werden, die in einer Ressourcen Datei gespeichert wurden. Weitere Informationen und Anweisungen zum Speichern von Zeitzonen finden Sie unter Gewusst [wie: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a>So deserialisieren Sie ein TimeZoneInfo-Objekt aus einer eingebetteten Ressource

1. Wenn die abzurufende Zeitzone keine benutzerdefinierte Zeitzone ist, versuchen Sie, Sie mit der <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>-Methode zu instanziieren.

2. Instanziieren Sie ein <xref:System.Resources.ResourceManager> Objekt, indem Sie den voll qualifizierten Namen der eingebetteten Ressourcen Datei und einen Verweis auf die Assembly, die die Ressourcen Datei enthält, übergeben.

   Wenn Sie den voll qualifizierten Namen der eingebetteten Ressourcen Datei nicht ermitteln können, verwenden Sie den [Ildasm. exe (IL-Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) , um das Assemblymanifest zu überprüfen. Ein `.mresource` Eintrag identifiziert die Ressource. Im Beispiel wird der voll qualifizierte Name der Ressource `SerializeTimeZoneData.SerializedTimeZones`.

   Wenn die Ressourcen Datei in dieselbe Assembly eingebettet ist, in der der Zeit Zonen-instanziationscode enthalten ist, können Sie einen Verweis darauf abrufen, indem Sie die `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A>-Methode aufrufen.

3. Wenn der Aufruf der <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>-Methode fehlschlägt oder eine benutzerdefinierte Zeitzone instanziiert werden soll, rufen Sie eine Zeichenfolge ab, die die serialisierte Zeitzone enthält, indem Sie die <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>-Methode aufrufen.

4. Deserialisieren Sie die Zeit Zonendaten, indem Sie die <xref:System.TimeZoneInfo.FromSerializedString%2A>-Methode aufrufen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein <xref:System.TimeZoneInfo> Objekt deserialisiert, das in einer eingebetteten .NET-XML-Ressourcen Datei gespeichert ist.

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

Dieser Code veranschaulicht die Ausnahmebehandlung, um sicherzustellen, dass ein <xref:System.TimeZoneInfo> für die Anwendung erforderliches Objekt vorhanden ist. Zuerst wird versucht, ein <xref:System.TimeZoneInfo> Objekt zu instanziieren, indem es mithilfe der <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>-Methode aus der Registrierung abgerufen wird. Wenn die Zeitzone nicht instanziiert werden kann, ruft der Code Sie aus der eingebetteten Ressourcen Datei ab.

Da Daten für benutzerdefinierte Zeitzonen (mit der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>-Methode instanziierte Zeitzonen) nicht in der Registrierung gespeichert werden, ruft der Code den <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> nicht auf, um die Zeitzone für Palmer, Antarktis zu instanziieren. Stattdessen sucht es sofort nach der eingebetteten Ressourcen Datei, um eine Zeichenfolge abzurufen, die die Daten der Zeitzone enthält, bevor Sie die <xref:System.TimeZoneInfo.FromSerializedString%2A>-Methode aufruft.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

- Dem Projekt wird ein Verweis auf "System. Windows. Forms. dll" und "System. Core. dll" hinzugefügt.

- Die folgenden Namespaces werden importiert:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
- [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)
- [Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
