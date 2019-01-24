---
title: 'Vorgehensweise: Verwenden von EdmGen.exe zum Überprüfen von Modell- und Zuordnungsdateien'
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: 87150aee8eac6a594b18b77230889c1208003dde
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566358"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a>Vorgehensweise: Verwenden von EdmGen.exe zum Überprüfen von Modell- und Zuordnungsdateien
In diesem Thema wird gezeigt, wie Sie mit der [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) Tool, um die Modell- und Zuordnungsdateien zu überprüfen. Weitere Informationen finden Sie unter [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a>So validieren Sie das Modell 'School' mit 'EdmGen.exe'  
  
1.  Erstellen der Datenbank "School". Weitere Informationen finden Sie unter [Erstellen der Beispieldatenbank "School"](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Erstellen des Modells "School" Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie zum Generieren von Modell- und Zuordnungsdateien EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a>Siehe auch
- [Vorgehensweise: Manuelles Konfigurieren eines Entity Framework-Projekts](https://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)
- [ADO.NET Entity Data Model Tools (ADO.NET Entity Data Model-Tools)](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
- [Vorgehensweise: Vorgenerieren von Ansichten zur Verbesserung der Abfrageleistung](https://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)
- [Vorgehensweise: Mithilfe von EdmGen.exe um Objektebenencode zu generieren.](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)
