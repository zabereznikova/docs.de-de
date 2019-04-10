---
title: 'Vorgehensweise: Überprüfen von DBML- und externen Zuordnungsdateien'
ms.date: 03/30/2017
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
ms.openlocfilehash: 83a26f22495c849aa00143ca36b63fa147120c28
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310238"
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a>Vorgehensweise: Überprüfen von DBML- und externen Zuordnungsdateien
Externe Zuordnungsdateien und von Ihnen geänderte .dbml-Dateien müssen hinsichtlich ihrer jeweiligen Schemadefinitionen überprüft werden. Dieses Thema enthält Visual Studio-Benutzer mit den Schritten zum Implementieren des Validierungsprozesses.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
### <a name="to-validate-a-dbml-or-xml-file"></a>So validieren Sie ein .dbml- oder eine XML-Datei  
  
1. Visual Studio **Datei** Startmenü **öffnen**, und klicken Sie dann auf **Datei**.  
  
2. In der **geöffnete Datei** Dialogfeld klicken Sie auf der DBML- oder XML-Zuordnungsdatei, die Sie überprüfen möchten.  
  
     Die Datei wird geöffnet, der **XML-Editor**.  
  
3. Mit der rechten Maustaste im Fensters, und klicken Sie dann auf **Eigenschaften**.  
  
4. In der **Eigenschaften** Fenster, klicken Sie auf die Auslassungspunkte für die **Schemas** Eigenschaft.  
  
     Die **XML-Schemas** Dialogfeld wird geöffnet.  
  
5. Beachten Sie die entsprechende Schemadefinition für den Zweck.  
  
    -   DbmlSchema.xsd ist die Schemadefinition zum Validieren einer .dbml-Datei. Weitere Informationen finden Sie unter [Codegenerierung in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
    -   LinqToSqlMapping.xsd ist die Schemadefinition zum Überprüfen einer externen XML-Zuordnungsdatei. Weitere Informationen finden Sie unter [externe Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
6. In der **verwenden** Spalte mit der gewünschten Schema Definition-Zeile, klicken Sie im Dropdown-Menü zu öffnen, und klicken Sie auf **dieses Schema verwenden**.  
  
     Die Schemadefinitionsdatei ist nun der DBML- oder XML-Zuordnungsdatei zugeordnet.  
  
     Stellen Sie sicher, dass keine anderen Schemadefinitionen ausgewählt werden.  
  
7. Auf der **Ansicht** Menü klicken Sie auf **Fehlerliste**.  
  
     Ermitteln Sie, ob Fehler, Warnungen oder Meldungen erzeugt wurden. Ist dies nicht der Fall, ist die XML-Datei für die Schemadefinition gültig.  
  
## <a name="alternate-method-for-supplying-schema-definition"></a>Alternative Methode zur Bereitstellung einer Schemadefinition  
 Wenn aus irgendeinem Grund die passende .xsd Datei nicht in angezeigt wird der **XML-Schemas** im Dialogfeld können Sie die XSD-Datei aus einem Hilfethema herunterladen. Die folgenden Schritte können Sie die speichern Sie der heruntergeladenen Datei im Unicode-Format von XML-Editor von Visual Studio erforderlich.  
  
#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a>So kopieren Sie eine Schemadefinitionsdatei aus einem Hilfethema  
  
1. Suchen Sie das Hilfethema, das die Schemadefinition enthält (siehe weiter oben in diesem Abschnitt).  
  
    -   .Dbml-Dateien finden Sie unter [Codegenerierung in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
    -   Externe Zuordnungsdateien finden Sie unter [externe Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
2. Klicken Sie auf **Code kopieren** , die Codedatei in die Zwischenablage zu kopieren.  
  
3. Starten Sie Editor, um eine neue Datei zu erstellen.  
  
4. Fügen Sie den Code aus der Zwischenablage in die Editor-Datei ein.  
  
5. Klicken Sie im Editor **Datei** Menü klicken Sie auf **speichern**.  
  
6. In der **Codierung** Kontrollkästchen **Unicode**.  
  
    > [!IMPORTANT]
    >  Diese Auswahl stellt sicher, dass die Unicode-16-Byte-Sortierungsmarkierung (`FFFE`) der Textdatei vorangestellt wird.  
  
7. In der **Dateiname** erstellen einen Dateinamen mit der Erweiterung XSD.  
  
## <a name="see-also"></a>Siehe auch

- [Referenz](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
