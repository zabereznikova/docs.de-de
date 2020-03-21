---
title: 'Gewusst wie: Generieren von Objektebenencode mit "EdmGen.exe"'
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: 1dbd2e25d5f9795af4f80e079c6a0b807666743d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150557"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a>Gewusst wie: Generieren von Objektebenencode mit "EdmGen.exe"
In diesem Thema wird gezeigt, wie Sie das Werkzeug [EDM-Generator (EdmGen.exe)](edm-generator-edmgen-exe.md) verwenden, um Objekt-Layer-Code basierend auf der .csdl-Datei zu generieren.  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>So generieren Sie mithilfe von EdmGen.exe den Objektebenencode für das Modell "School" für ein Visual Basic-Projekt  
  
1. Erstellen der Datenbank "School". Weitere Informationen finden Sie unter [Erstellen der Schulbeispieldatenbank](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Generieren Sie das Modell "School", oder verwenden Sie die Datei School.csdl. Weitere Informationen finden Sie unter [Gewusst wie: Verwenden von EdmGen.exe zum Generieren der Modell- und Zuordnungsdateien](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3. Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a>So generieren Sie mithilfe von EdmGen.exe den Objektebenencode für das Modell "School" für ein C#-Projekt  
  
1. Erstellen der Datenbank "School". Weitere Informationen finden Sie unter [Erstellen der Schulbeispieldatenbank](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Generieren Sie das Modell "School", oder verwenden Sie die Datei School.csdl. Weitere Informationen finden Sie unter [Gewusst wie: Verwenden von EdmGen.exe zum Generieren der Modell- und Zuordnungsdateien](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3. Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- [Modellieren und Zuordnen](modeling-and-mapping.md)
- [Gewusst wie: Manuelles Konfigurieren eines Entity Framework-Projekts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [ADO.NET Entity Data Model Tools (ADO.NET Entity Data Model-Tools)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Gewusst wie: Vorgenerieren von Ansichten zur Verbesserung der Abfrageleistung](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Gewusst wie: Generieren von Modell- und Zuordnungsdateien mit "EdmGen.exe"](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
