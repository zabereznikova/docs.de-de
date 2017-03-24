---
title: "In Dateiname angegebene Datei ist keine gültige XML-Datei | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2fa595ab411fdd300327db9e1fcca1e3156c7eed
ms.lasthandoff: 03/13/2017

---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a>Die in „Dateiname“ angegebene Datei ist keine gültige XML-Datei.
Der von Ihnen angegebene Dateiname gehört nicht zu einer gültigen XML-Datei. Sie können eine Dokumenttypdefinition (DTD), ein Microsoft XDR-Schemaformat (XML-Data Reduced) oder ein XSD-Schema (Sprache der XML-Schemadefinition) verwenden, um die zulässige Struktur und die Inhalte eines XML-Dokuments anzugeben. XSD-Schemas sind die bevorzugte Methode zum Angeben von XML-Grammatiken in der [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)].  
  
> [!NOTE]
>  In einigen früheren Versionen von Visual Studio stellt der **XML-Designer** den Designer für typisierte DataSets und XML-Schemas dar. Der **XML-Designer** kann weiterhin zum Erstellen und Bearbeiten von XML-Schemadateien verwendet werden. In [!INCLUDE[vs_current_long](../../csharp/misc/includes/vs_current_long_md.md)], der Designer zum Erstellen und Bearbeiten typisierter Datasets ist die **Dataset-Designer**. Weitere Informationen finden Sie unter [erstellen und Bearbeiten typisierter Datasets](https://docs.microsoft.com/visualstudio/data-tools/creating-and-editing-typed-datasets).  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Überprüfen Sie, ob Sie den richtigen Dateinamen angegeben haben.  
  
-   Überprüfen Sie, ob die angegebene Datei gültiges XML enthält, indem Sie die zu überprüfende XML-Datei im **XML-Designer**laden. Klicken Sie im Menü **XML** auf **XML überprüfen**. Fehler werden im Fenster **Aufgabenliste**angezeigt.  
  
-   Wenn der XML-Datei ein XML-Schema zugeordnet ist, überprüfen Sie, ob die Elemente in der definierten Struktur angezeigt werden und der Inhalt der einzelnen Elemente den im Schema angegebenen deklarierten Datentypen entspricht.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml></xref:System.Xml>   
 [Gewusst wie: Analysieren von Dateipfaden](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
