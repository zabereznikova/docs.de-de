---
title: "Die in „Dateiname“ angegebene Datei ist keine gültige XML-Datei."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f3275608a1871ac981eb5b3aa39f0be6ab4e758e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a>Die in „Dateiname“ angegebene Datei ist keine gültige XML-Datei.
Der von Ihnen angegebene Dateiname gehört nicht zu einer gültigen XML-Datei. Sie können eine Dokumenttypdefinition (DTD), ein Microsoft XDR-Schemaformat (XML-Data Reduced) oder ein XSD-Schema (Sprache der XML-Schemadefinition) verwenden, um die zulässige Struktur und die Inhalte eines XML-Dokuments anzugeben. XSD-Schemas sind die bevorzugte Methode zum Angeben von XML-Grammatiken im [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].  
  
> [!NOTE]
>  In einigen früheren Versionen von Visual Studio stellt der **XML-Designer** den Designer für typisierte DataSets und XML-Schemas dar. Der **XML-Designer** kann weiterhin zum Erstellen und Bearbeiten von XML-Schemadateien verwendet werden. In [!INCLUDE[vs_current_long](~/includes/vs-current-long-md.md)]ist der Designer zum Erstellen und Bearbeiten typisierter DataSets der **DataSet-Designer**. Weitere Informationen finden Sie unter [erstellen und Bearbeiten typisierter Datasets](/visualstudio/data-tools/creating-and-editing-typed-datasets).  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Überprüfen Sie, ob Sie den richtigen Dateinamen angegeben haben.  
  
-   Überprüfen Sie, ob die angegebene Datei gültiges XML enthält, indem Sie die zu überprüfende XML-Datei im **XML-Designer**laden. Klicken Sie im Menü **XML** auf **XML überprüfen**. Fehler werden im Fenster **Aufgabenliste**angezeigt.  
  
-   Wenn der XML-Datei ein XML-Schema zugeordnet ist, überprüfen Sie, ob die Elemente in der definierten Struktur angezeigt werden und der Inhalt der einzelnen Elemente den im Schema angegebenen deklarierten Datentypen entspricht.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml>  
 [Gewusst wie: Analysieren von Dateipfaden](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
