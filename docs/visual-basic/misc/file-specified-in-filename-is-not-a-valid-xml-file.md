---
title: Die in „Dateiname“ angegebene Datei ist keine gültige XML-Datei.
ms.date: 07/20/2015
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
ms.openlocfilehash: ffa39653c20127bb6af5e85654fee940a191fe5b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603523"
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a>Die in „Dateiname“ angegebene Datei ist keine gültige XML-Datei.
Der von Ihnen angegebene Dateiname gehört nicht zu einer gültigen XML-Datei. Sie können eine Dokumenttypdefinition (DTD), ein Microsoft XDR-Schemaformat (XML-Data Reduced) oder ein XSD-Schema (Sprache der XML-Schemadefinition) verwenden, um die zulässige Struktur und die Inhalte eines XML-Dokuments anzugeben. XSD-Schemas sind die bevorzugte Methode zum Angeben von XML-Grammatiken im [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].

> [!NOTE]
>  In einigen früheren Versionen von Visual Studio stellt der **XML-Designer** den Designer für typisierte DataSets und XML-Schemas dar. Der **XML-Designer** kann weiterhin zum Erstellen und Bearbeiten von XML-Schemadateien verwendet werden. In Visual Studio 2012 ist der Designer zum Erstellen und Bearbeiten typisierter Datasets jedoch die **Dataset-Designer**. Weitere Informationen finden Sie unter [erstellen und Bearbeiten typisierter Datasets](/visualstudio/data-tools/creating-and-editing-typed-datasets).

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

-   Überprüfen Sie, ob Sie den richtigen Dateinamen angegeben haben.

-   Überprüfen Sie, ob die angegebene Datei gültiges XML enthält, indem Sie die zu überprüfende XML-Datei im **XML-Designer**laden. Klicken Sie im Menü **XML** auf **XML überprüfen**. Fehler werden im Fenster **Aufgabenliste**angezeigt.

-   Wenn der XML-Datei ein XML-Schema zugeordnet ist, überprüfen Sie, ob die Elemente in der definierten Struktur angezeigt werden und der Inhalt der einzelnen Elemente den im Schema angegebenen deklarierten Datentypen entspricht.

## <a name="see-also"></a>Siehe auch

- <xref:System.Xml>
- [Vorgehensweise: Analysieren von Dateipfaden](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)