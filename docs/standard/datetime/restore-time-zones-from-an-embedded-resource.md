---
title: 'Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], deserializing
- time zones [.NET], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
ms.openlocfilehash: 1dd3dff2441ac5e21f3ebf97d58919a7c65d42c5
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063429"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a>Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource

In diesem Thema wird beschrieben, wie Zeitzonen wieder hergestellt werden, die in einer Ressourcen Datei gespeichert wurden. Weitere Informationen und Anweisungen zum Speichern von Zeitzonen finden Sie unter Gewusst [wie: Speichern von Zeitzonen in einer eingebetteten Ressource](save-time-zones-to-an-embedded-resource.md).

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a>So deserialisieren Sie ein TimeZoneInfo-Objekt aus einer eingebetteten Ressource

1. Wenn die abzurufende Zeitzone keine benutzerdefinierte Zeitzone ist, versuchen Sie, Sie mithilfe der-Methode zu instanziieren <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> .

2. Instanziieren <xref:System.Resources.ResourceManager> Sie ein-Objekt, indem Sie den voll qualifizierten Namen der eingebetteten Ressourcen Datei und einen Verweis auf die Assembly, die die Ressourcen Datei enthält, übergeben.

   Wenn Sie den voll qualifizierten Namen der eingebetteten Ressourcen Datei nicht ermitteln können, verwenden Sie den [Ildasm.exe (IL-Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) , um das Assemblymanifest zu überprüfen. Ein `.mresource` Eintrag identifiziert die Ressource. Im Beispiel lautet der voll qualifizierte Name der Ressource `SerializeTimeZoneData.SerializedTimeZones` .

   Wenn die Ressourcen Datei in dieselbe Assembly eingebettet ist, in der der Zeit Zonen-instanzierationscode enthalten ist, können Sie einen Verweis darauf abrufen, indem Sie die- `static` `Shared` Methode (in Visual Basic) aufrufen <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> .

3. Wenn der Aufruf der- <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> Methode fehlschlägt oder eine benutzerdefinierte Zeitzone instanziiert werden soll, rufen Sie eine Zeichenfolge ab, die die serialisierte Zeitzone enthält, indem Sie die- <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> Methode aufrufen.

4. Deserialisieren Sie die Zeit Zonendaten, indem Sie die- <xref:System.TimeZoneInfo.FromSerializedString%2A> Methode aufrufen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein-Objekt deserialisiert, das <xref:System.TimeZoneInfo> in einer eingebetteten .NET-XML-Ressourcen Datei gespeichert ist.

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

Dieser Code veranschaulicht die Ausnahmebehandlung, um sicherzustellen, dass ein <xref:System.TimeZoneInfo> für die Anwendung erforderliches-Objekt vorhanden ist. Zuerst wird versucht, ein-Objekt zu instanziieren, <xref:System.TimeZoneInfo> indem es mithilfe der-Methode aus der Registrierung abgerufen wird <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> . Wenn die Zeitzone nicht instanziiert werden kann, ruft der Code Sie aus der eingebetteten Ressourcen Datei ab.

Da Daten für benutzerdefinierte Zeitzonen (mit der-Methode instanziierte Zeitzonen <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> ) nicht in der Registrierung gespeichert werden, ruft der Code nicht <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> auf, um die Zeitzone für Palmer, Antarktis zu instanziieren. Stattdessen sucht es sofort nach der eingebetteten Ressourcen Datei, um eine Zeichenfolge abzurufen, die die Daten der Zeitzone enthält, bevor die-Methode aufgerufen wird <xref:System.TimeZoneInfo.FromSerializedString%2A> .

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

- Ein Verweis auf System.Windows.Forms.dll und System.Core.dll dem Projekt hinzugefügt werden.

- Die folgenden Namespaces werden importiert:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](index.md)
- [Übersicht über Zeitzonen](time-zone-overview.md)
- [Gewusst wie: Speichern von Zeitzonen in einer eingebetteten Ressource](save-time-zones-to-an-embedded-resource.md)
