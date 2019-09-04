---
title: 'Vorgehensweise: Generieren von Objektebenencode mit „EdmGen.exe“'
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: b85bacff093c268cd35dca2ede36e6ceb74ca4d1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251403"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a>Vorgehensweise: Generieren von Objektebenencode mit „EdmGen.exe“
In diesem Thema wird gezeigt, wie Sie das [EDM Generator-Tool (EdmGen. exe)](edm-generator-edmgen-exe.md) verwenden, um auf der Grundlage der CSDL-Datei Code auf Objektebene zu generieren.  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>So generieren Sie mithilfe von EdmGen.exe den Objektebenencode für das Modell "School" für ein Visual Basic-Projekt  
  
1. Erstellen der Datenbank "School". Weitere Informationen finden Sie unter [Erstellen der Beispieldatenbank "School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))".  
  
2. Generieren Sie das Modell "School", oder verwenden Sie die Datei School.csdl. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie EdmGen. exe, um die Modell-und](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)Zuordnungsdateien zu generieren.  
  
3. Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a>So generieren Sie mithilfe von EdmGen.exe den Objektebenencode für das Modell "School" für ein C#-Projekt  
  
1. Erstellen der Datenbank "School". Weitere Informationen finden Sie unter [Erstellen der Beispieldatenbank "School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))".  
  
2. Generieren Sie das Modell "School", oder verwenden Sie die Datei School.csdl. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie EdmGen. exe, um die Modell-und](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)Zuordnungsdateien zu generieren.  
  
3. Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Modellieren und Zuordnen](modeling-and-mapping.md)
- [Vorgehensweise: Manuelles Konfigurieren eines Entity Framework Projekts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [ADO.NET Entity Data Model Tools (ADO.NET Entity Data Model-Tools)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Vorgehensweise: Vorab Generieren von Sichten, um die Abfrageleistung zu verbessern](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Vorgehensweise: Verwenden von "EdmGen. exe" zum Generieren der Modell-und Zuordnungsdateien](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
