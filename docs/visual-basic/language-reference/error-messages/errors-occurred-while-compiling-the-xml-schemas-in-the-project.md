---
title: Fehler beim Kompilieren der XML-Schemas im Projekt | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36810
- vbc36810
dev_langs:
- VB
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
caps.latest.revision: 11
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
ms.openlocfilehash: cf04e85da98db53d1c78269169571936f708cd21
ms.lasthandoff: 03/13/2017

---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a>Fehler beim Kompilieren der XML-Schemas im Projekt
Fehler beim Kompilieren der XML-Schemas im Projekt. Aus diesem Grund ist IntelliSense für XML nicht verfügbar.  
  
 Es ist ein Fehler in einem XML-Schema Definition (XSD)-Schema, das im Projekt enthalten. Dieser Fehler tritt auf, wenn Sie eine XSD-Schemadatei (.xsd) hinzufügen, die Konflikte mit vorhandenen XSD-Schema für das Projekt festgelegt.  
  
 **Fehler-ID:** BC36810  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Doppelklicken Sie auf die Warnung in der **Fehlerliste** Fenster. Visual Basic gelangen Sie zu der Position in der XSD-Datei, die die Quelle der Warnung ist. Korrigieren Sie den Fehler im XSD-Schema.  
  
-   Stellen Sie sicher, dass alle erforderlichen XSD-Schemadateien (.xsd) im Projekt enthalten sind. Möglicherweise wird auf **alle Dateien anzeigen** auf der **Projekt** Menü, um die XSD-Dateien im **Projektmappen-Explorer**. Mit der rechten Maustaste einer XSD-Datei, und klicken Sie dann auf **zu Projekt** auf die Datei im Projekt enthalten.  
  
-   Wenn Sie das XML to Schema-Assistenten verwenden, wird dieser Fehler kann auftreten, wenn Sie Schemas mehr als einmal aus der gleichen Quelle ableiten. In diesem Fall fügen Sie eine neue XML zu Schema-Elementvorlage vorhandenen XSD-Schemadateien aus dem Projekt entfernen können hinzu, und stellen Sie dann die XML-Schema-Assistenten mit den entsprechenden XML-Datenquellen für das Projekt.  
  
-   Wenn kein Fehler im XSD-Schema angegeben wird, kann der XML-Compiler nicht genügend Informationen, um eine detaillierte Fehlermeldung haben. Sie können möglicherweise weitere Informationen zu erhalten, wenn Sie sicherstellen, dass die XML-Namespaces für die XSD-Dateien in Ihrem Projekt Übereinstimmung, die XML-Namespaces für das XML-Schemaset in Visual Studio identifiziert enthalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Fehlerliste (Fenster)](https://docs.microsoft.com/visualstudio/ide/reference/error-list-window)   
 [IntelliSense für XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
