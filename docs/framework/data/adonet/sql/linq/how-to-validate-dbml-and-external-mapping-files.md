---
title: 'Vorgehensweise: Überprüfen von DBML- und externen Zuordnungsdateien'
ms.date: 03/30/2017
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
ms.openlocfilehash: 212d65dfe998b825dd40e564756083ed685dff6f
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70041134"
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a>Vorgehensweise: Überprüfen von DBML- und externen Zuordnungsdateien

Externe Zuordnungsdateien und von Ihnen geänderte .dbml-Dateien müssen hinsichtlich ihrer jeweiligen Schemadefinitionen überprüft werden. In diesem Thema werden Visual Studio-Benutzern die Schritte zur Implementierung des Validierungsprozesses bereitstellt.

[!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]

### <a name="to-validate-a-dbml-or-xml-file"></a>So validieren Sie ein .dbml- oder eine XML-Datei

1. Zeigen Sie im Menü **Datei** von Visual Studio auf **Öffnen**, und klicken Sie dann auf **Datei**.

2. Klicken Sie im Dialogfeld **Datei öffnen** auf die DBML-oder XML-Zuordnungsdatei, die Sie überprüfen möchten.

    Die Datei wird im **XML-Editor**geöffnet.

3. Klicken Sie mit der rechten Maustaste auf das Fenster, und klicken Sie auf **Eigenschaften**.

4. Klicken Sie im Fenster **Eigenschaften** auf die Auslassungs Punkte für die Eigenschaft **Schemas** .

    Das Dialogfeld **XML-Schemas** wird geöffnet.

5. Beachten Sie die entsprechende Schemadefinition für den Zweck.

    - DbmlSchema.xsd ist die Schemadefinition zum Validieren einer .dbml-Datei. Weitere Informationen finden Sie unter [Code Generierung in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).

    - LinqToSqlMapping.xsd ist die Schemadefinition zum Überprüfen einer externen XML-Zuordnungsdatei. Weitere Informationen finden Sie unter [externe Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).

6. Klicken Sie in der Spalte **verwenden** der Zeile gewünschte Schema Definition auf, um das Dropdown Feld zu öffnen, und klicken Sie dann auf **dieses Schema verwenden**.

    Die Schemadefinitionsdatei ist nun der DBML- oder XML-Zuordnungsdatei zugeordnet.

    Stellen Sie sicher, dass keine anderen Schemadefinitionen ausgewählt werden.

7. Klicken Sie im Menü **Ansicht** auf **Fehlerliste**.

    Ermitteln Sie, ob Fehler, Warnungen oder Meldungen erzeugt wurden. Ist dies nicht der Fall, ist die XML-Datei für die Schemadefinition gültig.

## <a name="alternate-method-for-supplying-schema-definition"></a>Alternative Methode zur Bereitstellung einer Schemadefinition

Wenn die entsprechende XSD-Datei aus irgendeinem Grund nicht im Dialogfeld **XML-Schemas** angezeigt wird, können Sie die XSD-Datei aus einem Hilfethema herunterladen. Die folgenden Schritte unterstützen Sie beim Speichern der heruntergeladenen Datei im Unicode-Format, das vom XML-Editor von Visual Studio benötigt wird.

#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a>So kopieren Sie eine Schemadefinitionsdatei aus einem Hilfethema

1. Suchen Sie das Hilfethema, das die Schemadefinition enthält (siehe weiter oben in diesem Abschnitt).

    - Informationen zu DBML-Dateien finden Sie unter [Code Generierung in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).

    - Informationen zu externen Mapping-Dateien finden Sie unter [externe Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).

2. Klicken Sie auf **Code kopieren** , um die Codedatei in die Zwischenablage zu kopieren.

3. Starten Sie Editor, um eine neue Datei zu erstellen.

4. Fügen Sie den Code aus der Zwischenablage in die Editor-Datei ein.

5. Klicken Sie im Menü **Datei** auf **Speichern**unter.

6. Wählen Sie im Feld **Codierung** die Option **Unicode**aus.

    > [!IMPORTANT]
    > Diese Auswahl stellt sicher, dass die Unicode-16-Byte-Sortierungsmarkierung (`FFFE`) der Textdatei vorangestellt wird.

7. Erstellen Sie im Feld **Dateiname** einen Dateinamen mit der Erweiterung XSD.

## <a name="see-also"></a>Siehe auch

- [Verweis](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
