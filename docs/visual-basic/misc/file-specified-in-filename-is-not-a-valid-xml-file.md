---
title: Die in „Dateiname“ angegebene Datei ist keine gültige XML-Datei.
ms.date: 07/20/2015
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
ms.openlocfilehash: 1615722d19e1a24ee4e72bc702dbce3fe30411a4
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592892"
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a>Die in „Dateiname“ angegebene Datei ist keine gültige XML-Datei.

Der von Ihnen angegebene Dateiname gehört nicht zu einer gültigen XML-Datei. Sie können eine Dokumenttypdefinition (DTD), ein Microsoft XDR-Schemaformat (XML-Data Reduced) oder ein XSD-Schema (Sprache der XML-Schemadefinition) verwenden, um die zulässige Struktur und die Inhalte eines XML-Dokuments anzugeben. XSD-Schemas sind die bevorzugte Methode zum Angeben von XML-Grammatiken in .NET Framework.

> [!NOTE]
> In einigen früheren Versionen von Visual Studio stellt der **XML-Designer** den Designer für typisierte DataSets und XML-Schemas dar. Der **XML-Designer** kann weiterhin zum Erstellen und Bearbeiten von XML-Schemadateien verwendet werden. In Visual Studio 2012 ist der Designer zum Erstellen und Bearbeiten typisierter Datasets jedoch die **Dataset-Designer**. Weitere Informationen finden Sie unter [erstellen und Bearbeiten typisierter Datasets](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/314t4see(v=vs.120)).

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Überprüfen Sie, ob Sie den richtigen Dateinamen angegeben haben.

- Überprüfen Sie, ob die angegebene Datei gültiges XML enthält, indem Sie die zu überprüfende XML-Datei im **XML-Designer**laden. Klicken Sie im Menü **XML** auf **XML überprüfen**. Fehler werden im Fenster **Aufgabenliste**angezeigt.

- Wenn der XML-Datei ein XML-Schema zugeordnet ist, überprüfen Sie, ob die Elemente in der definierten Struktur angezeigt werden und der Inhalt der einzelnen Elemente den im Schema angegebenen deklarierten Datentypen entspricht.

## <a name="see-also"></a>Siehe auch

- <xref:System.Xml>
- [Vorgehensweise: Analysieren von Dateipfaden](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
