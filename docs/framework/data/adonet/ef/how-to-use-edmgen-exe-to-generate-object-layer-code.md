---
title: 'Gewusst wie: Generieren von Objektebenencode mit "EdmGen.exe"'
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: cd919f382096af6ff3e5e27225619767f3922ff0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a>Gewusst wie: Generieren von Objektebenencode mit "EdmGen.exe"
In diesem Thema zeigt, wie die [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) Tool zum Generieren von Objektebenencode auf Grundlage der CSDL-Datei.  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>So generieren Sie mithilfe von EdmGen.exe den Objektebenencode für das Modell "School" für ein Visual Basic-Projekt  
  
1.  Erstellen der Datenbank "School". Weitere Informationen finden Sie unter [Erstellen der Beispieldatenbank "School"](http://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Generieren Sie das Modell "School", oder verwenden Sie die Datei School.csdl. Weitere Informationen finden Sie unter [Vorgehensweise: verwenden EdmGen.exe generiert die Modell- und Zuordnen von Dateien](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a>So generieren Sie mithilfe von EdmGen.exe den Objektebenencode für das Modell "School" für ein C#-Projekt  
  
1.  Erstellen der Datenbank "School". Weitere Informationen finden Sie unter [Erstellen der Beispieldatenbank "School"](http://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Generieren Sie das Modell "School", oder verwenden Sie die Datei School.csdl. Weitere Informationen finden Sie unter [Vorgehensweise: verwenden EdmGen.exe generiert die Modell- und Zuordnen von Dateien](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Modellieren und Zuordnen](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [Vorgehensweise: Manuelles Konfigurieren ein Entity Framework-Projekts](http://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [ADO.NET Entity Data Model Tools (ADO.NET Entity Data Model-Tools)](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)  
 [Vorgehensweise: Vorabgenerieren von Sichten, um die Abfrageleistung zu verbessern.](http://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [Vorgehensweise: Generieren von Modell- und Zuordnungsdateien mit „EdmGen.exe“](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
