---
title: 'Vorgehensweise: Generieren von Modell- und Zuordnungsdateien mit „EdmGen.exe“'
ms.date: 03/30/2017
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
ms.openlocfilehash: 8837afd05eec0eaf8ef3e909d46b280e8ae05da7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198183"
---
# <a name="how-to-use-edmgenexe-to-generate-the-model-and-mapping-files"></a>Vorgehensweise: Generieren von Modell- und Zuordnungsdateien mit „EdmGen.exe“

In diesem Thema wird veranschaulicht, wie das Tool EDM-Generator (EdmGen.exe) verwendet wird, um die folgenden Dateien auf der Grundlage der Datenbank "School" zu generieren:  
  
- Ein konzeptionelles Modell (eine CSDL-Datei).  
  
- Ein Speichermodell (eine SSDL-Datei).  
  
- Die Zuordnung zwischen dem konzeptionellen Modell und dem Speichermodell (eine MSL-Datei).  
  
- Code auf Objektebene für Visual Basic oder C#.  
  
- Ansichtsdateien.  
  
 Wenn das Tool EdmGen.exe mit dem Befehl /mode:FullGeneration aufgerufen wird, werden die oben aufgeführten Dateien generiert. Weitere Informationen zu EdmGen.exe-Befehlen finden Sie unter [EDM-Generator (EdmGen.exe)](edm-generator-edmgen-exe.md).  
  
 Wenn Sie EdmGen.exe verwenden, um die Modell-und Mapping-Dateien zu generieren, müssen Sie das Visual Studio-Projekt für die Verwendung der Entity Framework konfigurieren. Weitere Informationen finden Sie unter Vorgehens [Weise: Manuelles Konfigurieren eines Entity Framework Projekts](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).  
  
> [!NOTE]
> Ein mithilfe von EdmGen.exe erstelltes konzeptionelles Modell enthält alle Objekte der Datenbank. Sie können mithilfe des Entity Data Model-Assistenten ein konzeptionelles Modell erstellen, das nur bestimmte Objekte enthält. Weitere Informationen finden Sie unter Gewusst [wie: Verwenden des Entity Data Model-Assistenten](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
### <a name="to-generate-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>So erstellen Sie mithilfe von 'EdmGen.exe' das Modell 'School' für ein Visual Basic-Projekt  
  
1. Erstellen der Datenbank "School". Weitere Informationen finden Sie unter [Erstellen der Beispieldatenbank "School](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))".  
  
2. Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
    ```  
  
### <a name="to-generate-the-school-model-for-a-c-project-using-edmgenexe"></a>So erstellen Sie mithilfe von 'EdmGen.exe' das Modell 'School' für ein C#-Projekt  
  
1. Erstellen der Datenbank "School". Weitere Informationen finden Sie unter [Erstellen der Beispieldatenbank "School](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))".  
  
2. Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- [Modellieren und Zuordnen](modeling-and-mapping.md)
- [Gewusst wie: Manuelles Konfigurieren eines Entity Framework-Projekts](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Gewusst wie: Vorgenerieren von Ansichten zur Verbesserung der Abfrageleistung](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [ADO.NET-Entity Data Model Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Vorgehensweise: Überprüfen von Modell- und Zuordnungsdateien mit „EdmGen.exe“](how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)
