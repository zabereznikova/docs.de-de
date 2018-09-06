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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99d38b336b5e655dd1c96682eec90c5fbe8469d6
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43885297"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a>Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource

Dieses Thema beschreibt die Vorgehensweise beim Wiederherstellen von Zeitzonen, die in einer Ressourcendatei gespeichert wurden. Weitere Informationen und Anweisungen zum Speichern von Zeitzonen finden Sie unter [Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a>Beim Deserialisieren eines TimeZoneInfo-Objekts aus einer eingebetteten Ressource

1. Wenn die Zeitzone abgerufen werden sollen, keine benutzerdefinierte Zeitzone ist, versuchen Sie es mit instanziiert die <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> Methode.

2. Instanziieren einer <xref:System.Resources.ResourceManager> -Objekts durch Übergeben der vollqualifizierte Name der eingebetteten Ressourcendatei und einem Verweis auf die Assembly, die die Ressourcendatei enthält.

   Wenn Sie den vollqualifizierten Namen der eingebetteten Ressourcendatei können nicht ermitteln, verwenden die [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) Manifest der Assembly zu untersuchen. Ein `.mresource` Eintrag identifiziert die Ressource. Im Beispiel des vollqualifizierten Ressourcennamens ist `SerializeTimeZoneData.SerializedTimeZones`.

   Wenn die Ressourcendatei in der gleichen Assembly, die den Instanziierungscode Zeitzone enthält eingebettet ist, können Sie einen Verweis darauf abrufen, durch den Aufruf der `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> Methode.

3. Wenn der Aufruf der <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> -Methode fehlschlägt, oder ist eine benutzerdefinierte Zeitzone instanziiert werden, rufen Sie eine Zeichenfolge, die durch den Aufruf der serialisierten Zeitzone enthält die <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> Methode.

4. Deserialisiert die Zeitzonendaten durch Aufrufen der <xref:System.TimeZoneInfo.FromSerializedString%2A> Methode.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird deserialisiert eine <xref:System.TimeZoneInfo> gespeichert, die in einer eingebetteten Ressourcendatei von .NET XML-Objekt.

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

Dieser Code veranschaulicht die Behandlung von Ausnahmen, um sicherzustellen, dass eine <xref:System.TimeZoneInfo> von der Anwendung benötigte Objekt vorhanden ist. Zuerst wird versucht, instanziieren Sie ein <xref:System.TimeZoneInfo> Objekt durch Abrufen aus der Registrierung mithilfe der <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> Methode. Wenn die Zeitzone nicht instanziiert werden kann, ruft Sie der Code aus der eingebetteten Ressourcendatei ab.

Da Daten für benutzerdefinierte Zeitzonen (Zeitzonen instanziiert werden mithilfe der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode) werden nicht gespeichert in der Registrierung wird der Code nicht Aufrufen der <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> instanziieren Sie die Zeitzone für Palmer, Antarktis. Stattdessen es sofort überprüft, die eingebettete Ressourcendatei aus, um eine Zeichenfolge abzurufen, das die Zeitzone-Daten enthält, vor dem Aufrufen der <xref:System.TimeZoneInfo.FromSerializedString%2A> Methode.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

* Dass das Projekt ein Verweis auf "System.Windows.Forms.dll" und "System.Core.dll" hinzugefügt werden.

* Dass die folgenden Namespaces importiert werden:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Siehe auch

* [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
* [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)
* [Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
