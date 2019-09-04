---
title: 'Vorgehensweise: Generieren von Modell- und Zuordnungsdateien mit „EdmGen.exe“'
ms.date: 03/30/2017
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
ms.openlocfilehash: 141b19c545360f92c2689252cf9aefd1ef156cf0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251424"
---
# <a name="how-to-use-edmgenexe-to-generate-the-model-and-mapping-files"></a>Vorgehensweise: Generieren von Modell- und Zuordnungsdateien mit „EdmGen.exe“
In diesem Thema wird veranschaulicht, wie das Tool EDM-Generator (EdmGen.exe) verwendet wird, um die folgenden Dateien auf der Grundlage der Datenbank "School" zu generieren:  
  
- Ein konzeptionelles Modell (eine CSDL-Datei).  
  
- Ein Speichermodell (eine SSDL-Datei).  
  
- Die Zuordnung zwischen dem konzeptionellen Modell und dem Speichermodell (eine MSL-Datei).  
  
- Code auf Objektebene für Visual Basic oder C#.  
  
- Ansichtsdateien.  
  
 Wenn das Tool EdmGen.exe mit dem Befehl /mode:FullGeneration aufgerufen wird, werden die oben aufgeführten Dateien generiert. Weitere Informationen zu "EdmGen. exe"-Befehlen finden Sie unter [EDM Generator (EdmGen. exe)](edm-generator-edmgen-exe.md).  
  
 Wenn Sie "EdmGen. exe" verwenden, um die Modell-und Zuordnungsdateien zu generieren, müssen Sie das Visual Studio [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Projekt für die Verwendung von konfigurieren. Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Konfigurieren eines Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))Projekts.  
  
> [!NOTE]
> Ein mithilfe von EdmGen.exe erstelltes konzeptionelles Modell enthält alle Objekte der Datenbank. Sie können mithilfe des Entity Data Model-Assistenten ein konzeptionelles Modell erstellen, das nur bestimmte Objekte enthält. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie den Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))-Assistenten.  
  
### <a name="to-generate-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>So erstellen Sie mithilfe von 'EdmGen.exe' das Modell 'School' für ein Visual Basic-Projekt  
  
1. Erstellen der Datenbank "School". Weitere Informationen finden Sie unter [Erstellen der Beispieldatenbank "School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))".  
  
2. Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
    ```  
  
### <a name="to-generate-the-school-model-for-a-c-project-using-edmgenexe"></a>So erstellen Sie mithilfe von 'EdmGen.exe' das Modell 'School' für ein C#-Projekt  
  
1. Erstellen der Datenbank "School". Weitere Informationen finden Sie unter [Erstellen der Beispieldatenbank "School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))".  
  
2. Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Modellieren und Zuordnen](modeling-and-mapping.md)
- [Vorgehensweise: Manuelles Konfigurieren eines Entity Framework Projekts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Vorgehensweise: Vorab Generieren von Sichten, um die Abfrageleistung zu verbessern](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [ADO.NET-Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Vorgehensweise: Verwenden von EdmGen. exe zum Überprüfen von Modell-und Zuordnungsdateien](how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)
