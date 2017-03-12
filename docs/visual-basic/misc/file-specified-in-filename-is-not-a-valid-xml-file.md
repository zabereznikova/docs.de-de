---
title: "Die in „Dateiname“ angegebene Datei ist keine g&#252;ltige XML-Datei. | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Die in „Dateiname“ angegebene Datei ist keine g&#252;ltige XML-Datei.
Der von Ihnen angegebene Dateiname gehört nicht zu einer gültigen XML\-Datei. Sie können eine Dokumenttypdefinition \(DTD\), ein Microsoft XDR\-Schemaformat \(XML\-Data Reduced\) oder ein XSD\-Schema \(Sprache der XML\-Schemadefinition\) verwenden, um die zulässige Struktur und die Inhalte eines XML\-Dokuments anzugeben. XSD\-Schemas sind die bevorzugte Methode zum Angeben von XML\-Grammatiken im [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort-md.md)].  
  
> [!NOTE]
>  In einigen früheren Versionen von Visual Studio stellt der **XML\-Designer** den Designer für typisierte DataSets und XML\-Schemas dar. Der **XML\-Designer** kann weiterhin zum Erstellen und Bearbeiten von XML\-Schemadateien verwendet werden. In [!INCLUDE[vs_current_long](../../csharp/misc/includes/vs-current-long-md.md)] ist der Designer zum Erstellen und Bearbeiten typisierter DataSets der **DataSet\-Designer**. Weitere Informationen finden Sie unter [Erstellen und Bearbeiten von typisierten Datasets](/visual-studio/data-tools/creating-and-editing-typed-datasets).  
  
### So beheben Sie diesen Fehler  
  
-   Überprüfen Sie, ob Sie den richtigen Dateinamen angegeben haben.  
  
-   Überprüfen Sie, ob die angegebene Datei gültiges XML enthält, indem Sie die zu überprüfende XML\-Datei im **XML\-Designer** laden. Klicken Sie im Menü **XML** auf **XML überprüfen**. Fehler werden im Fenster **Aufgabenliste** angezeigt.  
  
-   Wenn der XML\-Datei ein XML\-Schema zugeordnet ist, überprüfen Sie, ob die Elemente in der definierten Struktur angezeigt werden und der Inhalt der einzelnen Elemente den im Schema angegebenen deklarierten Datentypen entspricht.  
  
## Siehe auch  
 <xref:System.Xml>   
 [Gewusst wie: Analysieren von Dateipfaden](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)