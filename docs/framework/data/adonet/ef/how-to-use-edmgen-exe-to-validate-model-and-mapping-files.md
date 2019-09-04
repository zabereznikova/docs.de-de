---
title: 'Vorgehensweise: Überprüfen von Modell- und Zuordnungsdateien mit „EdmGen.exe“'
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: 4495ff3c5d55779e9db113a2a59361b643841382
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251382"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a>Vorgehensweise: Überprüfen von Modell- und Zuordnungsdateien mit „EdmGen.exe“
In diesem Thema wird gezeigt, wie Sie das Tool [EDM Generator (EdmGen. exe)](edm-generator-edmgen-exe.md) verwenden, um die Modell-und Zuordnungsdateien zu validieren. Weitere Informationen finden Sie unter [Entity Data Model](../entity-data-model.md).  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a>So validieren Sie das Modell 'School' mit 'EdmGen.exe'  
  
1. Erstellen der Datenbank "School". Weitere Informationen finden Sie unter [Erstellen der Beispieldatenbank "School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))".  
  
2. Erstellen des Modells "School" Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie EdmGen. exe, um die Modell-und](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)Zuordnungsdateien zu generieren.  
  
3. Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Manuelles Konfigurieren eines Entity Framework Projekts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [ADO.NET-Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Vorgehensweise: Vorab Generieren von Sichten, um die Abfrageleistung zu verbessern](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Vorgehensweise: Verwenden von "EdmGen. exe" zum Generieren von objektebenencode](how-to-use-edmgen-exe-to-generate-object-layer-code.md)
