---
title: Technologiebeispiel für versionstolerante Serialisierung
ms.date: 03/30/2017
ms.assetid: 2a183664-bfbf-4ff0-96f6-c836284ea916
ms.openlocfilehash: 317a47d46b839417e01eed9deca2459a96aaa201
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960779"
---
# <a name="version-tolerant-serialization-technology-sample"></a>Technologiebeispiel für versionstolerante Serialisierung
[Beispiel herunterladen](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/VTS.zip.exe)  
  
 In diesem Beispiel werden die Funktionen für die Versionstoleranz von .NET Serialisierung veranschaulicht. Im Beispiel werden Anwendungen erstellt, die zum Serialisieren und Deserialisieren von Daten andere Versionen von <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> verwenden. Obwohl verschiedene Typversionen verwendet werden, kommunizieren die Anwendungen reibungslos miteinander. Weitere Informationen finden Sie unter [Versionstolerante Serialisierung](../../../docs/standard/serialization/version-tolerant-serialization.md).  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a>So erstellen Sie das Beispiel mithilfe der Eingabeaufforderung  
  
1. Öffnen Sie ein Eingabeaufforderungsfenster, und navigieren Sie zu einem der sprachspezifischen Unterverzeichnisse (unter V1 Application oder V2 Application) für das Beispiel.  
  
2. Geben Sie in die Befehlszeile **msbuild.exe \<ver> application.sln** ein (wobei „\<ver>“ entweder v1 oder v2 entspricht).  
  
### <a name="to-build-the-sample-using-visual-studio"></a>So erstellen Sie das Beispiel mithilfe von Visual Studio  
  
1. Öffnen Sie den Datei-Explorer, und navigieren Sie zu einem der sprachspezifischen Unterverzeichnisse für das Beispiel.  
  
2. Navigieren Sie zum Unterverzeichnis V1 Application in dem Verzeichnis, das Sie im vorherigen Schritt ausgewählt haben.  
  
3. Doppelklicken Sie auf das Symbol für V1 Application.sln, um die Datei in Visual Studio zu öffnen.  
  
4. Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
5. Navigieren Sie zum Unterverzeichnis V2 Application, und wiederholen Sie die beiden vorherigen Schritte, um die V2-Anwendung zu erstellen.  
  
 Die Anwendungen werden im Standardunterverzeichnis \bin oder \bin\Debug des zugehörigen Projektverzeichnisses erstellt.  
  
### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
  
1. Navigieren Sie im Eingabeaufforderungsfenster zu dem sprachspezifischen Unterverzeichnis, das Sie beim Erstellen der Beispielanwendungen ausgewählt haben.  
  
2. Geben Sie **runme.cmd** in der Befehlszeile ein, um sofort beide Anwendungen auszuführen.  
  
 Alternativ können Sie zu den Verzeichnissen navigieren, die die neuen ausführbaren Dateien enthalten, und diese dann nacheinander ausführen.  
  
> [!NOTE]
> In diesem Beispiel werden Konsolenanwendungen erstellt. Sie müssen diese in einem Eingabeaufforderungsfenster starten und ausführen, um die Ausgabe anzuzeigen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>
- <xref:System.IO.FileStream>
