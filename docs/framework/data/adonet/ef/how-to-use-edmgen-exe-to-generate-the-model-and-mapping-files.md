---
title: 'Gewusst wie: Generieren von Modell- und Zuordnungsdateien mit "EdmGen.exe"'
ms.date: 03/30/2017
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
ms.openlocfilehash: ee8297c0833378b2b44800355b47db9caa2dc7fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150512"
---
# <a name="how-to-use-edmgenexe-to-generate-the-model-and-mapping-files"></a>Gewusst wie: Generieren von Modell- und Zuordnungsdateien mit "EdmGen.exe"
In diesem Thema wird veranschaulicht, wie das Tool EDM-Generator (EdmGen.exe) verwendet wird, um die folgenden Dateien auf der Grundlage der Datenbank "School" zu generieren:  
  
- Ein konzeptionelles Modell (eine CSDL-Datei).  
  
- Ein Speichermodell (eine SSDL-Datei).  
  
- Die Zuordnung zwischen dem konzeptionellen Modell und dem Speichermodell (eine MSL-Datei).  
  
- Code auf Objektebene für Visual Basic oder C#.  
  
- Ansichtsdateien.  
  
 Wenn das Tool EdmGen.exe mit dem Befehl /mode:FullGeneration aufgerufen wird, werden die oben aufgeführten Dateien generiert. Weitere Informationen zu EdmGen.exe-Befehlen finden Sie unter [EDM Generator (EdmGen.exe)](edm-generator-edmgen-exe.md).  
  
 Wenn Sie EdmGen.exe zum Generieren der Modell- und Zuordnungsdateien verwenden, müssen Sie ihr Visual Studio-Projekt dennoch für die Verwendung von Entity Framework konfigurieren. Weitere Informationen finden Sie unter [Gewusst wie: Manuelle Konfiguration eines Entity Framework-Projekts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).  
  
> [!NOTE]
> Ein mithilfe von EdmGen.exe erstelltes konzeptionelles Modell enthält alle Objekte der Datenbank. Sie können mithilfe des Entity Data Model-Assistenten ein konzeptionelles Modell erstellen, das nur bestimmte Objekte enthält. Weitere Informationen finden Sie unter [Gewusst wie: Verwenden des Entitätsdatenmodell-Assistenten](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
### <a name="to-generate-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>So erstellen Sie mithilfe von 'EdmGen.exe' das Modell 'School' für ein Visual Basic-Projekt  
  
1. Erstellen der Datenbank "School". Weitere Informationen finden Sie unter [Erstellen der Schulbeispieldatenbank](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
    ```  
  
### <a name="to-generate-the-school-model-for-a-c-project-using-edmgenexe"></a>So erstellen Sie mithilfe von 'EdmGen.exe' das Modell 'School' für ein C#-Projekt  
  
1. Erstellen der Datenbank "School". Weitere Informationen finden Sie unter [Erstellen der Schulbeispieldatenbank](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- [Modellieren und Zuordnen](modeling-and-mapping.md)
- [Gewusst wie: Manuelles Konfigurieren eines Entity Framework-Projekts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Gewusst wie: Vorgenerieren von Ansichten zur Verbesserung der Abfrageleistung](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [ADO.NET Tools für Entitätsdatenmodell](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Gewusst wie: Überprüfen von Modell- und Zuordnungsdateien mit "EdmGen.exe"](how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)
