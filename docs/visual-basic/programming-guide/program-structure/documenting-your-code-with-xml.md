---
title: Dokumentieren von Code mit XML (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML, documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2ec4907ff96a0861f97de21bdf45662c558d0a95
ms.lasthandoff: 03/13/2017

---
# <a name="documenting-your-code-with-xml-visual-basic"></a>Dokumentieren von Code mit XML (Visual Basic)
In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], Sie können den Code mit XML dokumentieren  
  
## <a name="xml-documentation-comments"></a>XML-Dokumentationskommentare  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]bietet eine einfache Möglichkeit zum automatischen Erstellen von XML-Dokumentation für Projekte. Sie können automatisch generiert ein XML-Skelett für Ihre Typen und Member und geben Sie dann für jeden Parameter und andere Hinweise Zusammenfassungen, beschreibende Dokumentation. Mit der entsprechenden Konfiguration wird die XML-Dokumentation automatisch in eine XML-Datei mit demselben Namen wie das Projekt und die Erweiterung ".xml" ausgegeben. Weitere Informationen finden Sie unter [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
 Die XML-Datei genutzt oder als XML bearbeitet werden. Diese Datei befindet sich im gleichen Verzeichnis wie die Ausgabe .exe oder .dll-Datei des Projekts.  
  
 XML-Dokumentation beginnt mit `'''`. Die Verarbeitung dieser Kommentare weist einige Einschränkungen auf:  
  
-   Die Dokumentation muss wohlgeformt sein XML. Wenn das XML nicht wohlgeformt ist, wird eine Warnung generiert, und die Dokumentationsdatei enthält einen Kommentar, der besagt, dass ein Fehler aufgetreten ist.  
  
-   Entwickler können ihre eigenen Satz von Tags zu erstellen. Es gibt ein Reihe empfohlener Tags (siehe "Verwandte Abschnitte" in diesem Thema). Einige der empfohlenen Tags haben eine besondere Bedeutung:  
  
    -   Die \<Param > Tag wird verwendet, um Parameter zu beschreiben. Wenn verwendet, stellt der Compiler sicher, dass der Parameter vorhanden ist und dass alle Parameter in der Dokumentation beschrieben werden. Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.  
  
    -   Die `cref` Attribut angefügt werden kann, um alle Tags, um einen Verweis auf ein Codeelement bereitzustellen. Der Compiler überprüft, ob dieses Codeelement vorhanden ist. Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus. Der Compiler berücksichtigt auch alle `Imports` Anweisungen, die bei der Suche für einen Typ, der gemäß der `cref` Attribut.  
  
    -   Die \<Zusammenfassung > Tag werden von IntelliSense im [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] zusätzliche Informationen über einen Typ oder Member angezeigt.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 Weitere Informationen zum Erstellen einer XML-Datei mit Dokumentationskommentaren finden Sie unter den folgenden Themen:  
  
-   [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [Verarbeiten der XML-Datei](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [Gewusst wie: Erstellen einer XML-Dokumentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [XML-Tools in Visual Studio](https://docs.microsoft.com/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a>Siehe auch  
 [Anwendungsentwicklung mit Visual Basic](../../../visual-basic/developing-apps/index.md)   
 [Visual Basic-Programmierhandbuch](../../../visual-basic/programming-guide/index.md)
