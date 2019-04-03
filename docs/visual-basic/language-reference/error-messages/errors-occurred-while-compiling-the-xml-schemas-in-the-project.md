---
title: Fehler beim Kompilieren der XML-Schemas im Projekt
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 337fc1fb4dfc83c9b4814d3e45eb0cbe0758f7ce
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842524"
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a>Fehler beim Kompilieren der XML-Schemas im Projekt
Fehler beim Kompilieren der XML-Schemas im Projekt. Aus diesem Grund ist die XML-IntelliSense nicht verfügbar.  
  
 Es ist ein Fehler in einem XML-Schema Definition (XSD)-Schema, das im Projekt enthalten ist. Dieser Fehler tritt auf, wenn Sie eine XSD-Schemadatei (.xsd) hinzufügen, die Konflikte mit vorhandenen XSD-Schema für das Projekt festgelegt.  
  
 **Fehler-ID:** BC36810  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Doppelklicken Sie auf die Warnung in der **Fehlerliste** Fenster. Visual Basic gelangen Sie zu der Position in der XSD-Datei, die die Quelle der Warnung ist. Korrigieren Sie den Fehler in der XSD-Schema.  
  
-   Stellen Sie sicher, dass alle erforderlichen XSD-Schemadateien (.xsd) im Projekt enthalten sind. Möglicherweise müssen Sie auf klicken **alle Dateien anzeigen** auf die **Projekt** Menü, um die XSD-Dateien im **Projektmappen-Explorer**. Mit der rechten Maustaste einer XSD-Datei, und klicken Sie dann auf **zu Projekt** auf die Datei in Ihr Projekt einbinden.  
  
-   Wenn Sie das XML to Schema-Assistenten verwenden, wird dieser Fehler kann auftreten, wenn Sie Schemas mehrmals aus derselben Quelle ableiten. In diesem Fall fügen Sie eine neue XML Schema-Elementvorlage, die vorhandenen XSD-Schema-Dateien aus dem Projekt entfernen können, und geben Sie dann die XML-Schema-Assistenten mit den entsprechenden XML-Datenquellen für Ihr Projekt.  
  
-   Wenn kein Fehler im XSD-Schema identifiziert wird, möglicherweise der XML-Compiler nicht genügend Informationen, um eine detaillierte Fehlermeldung bereitzustellen. Möglicherweise können Sie detailliertere Fehlerinformationen erhalten, wenn Sie sicherstellen, dass die XML-Namespaces für die XSD-Dateien in Ihrem Projekt Übereinstimmung, die XML-Namespaces, die für das XML-Schemaset in Visual Studio identifiziert enthalten.  
  
## <a name="see-also"></a>Siehe auch

- [Fenster „Fehlerliste“](/visualstudio/ide/reference/error-list-window)
- [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
