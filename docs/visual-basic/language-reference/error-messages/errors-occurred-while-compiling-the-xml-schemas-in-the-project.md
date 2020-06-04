---
title: Fehler beim Kompilieren der XML-Schemas im Projekt
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 919c6873ba63addb776d756a58c44a3fe3f0ec3d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409626"
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a>Fehler beim Kompilieren der XML-Schemas im Projekt
Fehler beim Kompilieren der XML-Schemas im Projekt. Aus diesem Grund ist XML IntelliSense nicht verfügbar.  
  
 Fehler in einem XSD-Schema (XML Schema Definition), das im Projekt enthalten ist. Dieser Fehler tritt auf, wenn Sie eine XSD-Schema Datei (XSD-Datei) hinzufügen, die in Konflikt mit dem vorhandenen XSD-Schemaset für das Projekt steht.  
  
 **Fehler-ID:** BC36810  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Doppelklicken Sie im Fenster **Fehlerliste** auf die Warnung. Visual Basic gelangen Sie zu dem Speicherort in der XSD-Datei, der die Quelle der Warnung ist. Korrigieren Sie den Fehler im XSD-Schema.  
  
- Stellen Sie sicher, dass alle erforderlichen XSD-Schema Dateien (XSD-Dateien) im Projekt enthalten sind. Möglicherweise müssen Sie im Menü **Projekt** auf **alle Dateien anzeigen** klicken, um die XSD-Dateien in **Projektmappen-Explorer**anzuzeigen. Klicken Sie mit der rechten Maustaste auf eine XSD-Datei, und klicken Sie dann auf **in Projekt einschließen** , um die Datei in das Projekt einzubeziehen.  
  
- Wenn Sie den XML-zu-Schema-Assistenten verwenden, kann dieser Fehler auftreten, wenn Sie Schemas mehr als einmal aus derselben Quelle ableiten. In diesem Fall können Sie die vorhandenen XSD-Schema Dateien aus dem Projekt entfernen, eine neue XML-Schema Element Vorlage hinzufügen und dann den XML-Schema-Assistenten mit allen anwendbaren XML-Quellen für das Projekt bereitstellen.  
  
- Wenn kein Fehler in Ihrem XSD-Schema identifiziert wird, verfügt der XML-Compiler möglicherweise nicht über genügend Informationen, um eine ausführliche Fehlermeldung bereitzustellen. Möglicherweise erhalten Sie ausführlichere Fehlerinformationen, wenn Sie sicherstellen, dass die XML-Namespaces für die XSD-Dateien, die im Projekt enthalten sind, mit den XML-Namespaces identisch sind, die für das XML-Schema in Visual Studio festgelegt wurden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Fehlerliste Fenster](/visualstudio/ide/reference/error-list-window)
- [XML](../../programming-guide/language-features/xml/index.md)
