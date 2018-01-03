---
title: "Gewusst wie: Überprüfen von DBML- und externen Zuordnungsdateien"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 9339176cbc6a72d940e3fa053c0e54e0667193f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a>Gewusst wie: Überprüfen von DBML- und externen Zuordnungsdateien
Externe Zuordnungsdateien und von Ihnen geänderte .dbml-Dateien müssen hinsichtlich ihrer jeweiligen Schemadefinitionen überprüft werden. Dieser Abschnitt bietet [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]-Benutzern Informationen zu den Schritten für das Implementieren des Validierungsprozesses.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
### <a name="to-validate-a-dbml-or-xml-file"></a>So validieren Sie ein .dbml- oder eine XML-Datei  
  
1.  Visual Studio **Datei** Sie im Menü **öffnen**, und klicken Sie dann auf **Datei**.  
  
2.  In der **Dateiöffnungsmodus** Dialogfeld klicken Sie auf der DBML- oder XML-Zuordnungsdatei, die Sie überprüfen möchten.  
  
     Die Datei wird geöffnet, der **XML-Editor**.  
  
3.  Mit der rechten Maustaste in des Fensters, und klicken Sie dann auf **Eigenschaften**.  
  
4.  In der **Eigenschaften** Fenster, klicken Sie auf die Schaltfläche für die **Schemas** Eigenschaft.  
  
     Die **XML-Schemas** Dialogfeld wird geöffnet.  
  
5.  Beachten Sie die entsprechende Schemadefinition für den Zweck.  
  
    -   DbmlSchema.xsd ist die Schemadefinition zum Validieren einer .dbml-Datei. Weitere Informationen finden Sie unter [Codegenerierung in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
    -   LinqToSqlMapping.xsd ist die Schemadefinition zum Überprüfen einer externen XML-Zuordnungsdatei. Weitere Informationen finden Sie unter [externe Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
6.  In der **verwenden** Spalte der gewünschten Schema Definition Zeile, klicken Sie zum Öffnen Sie das Dropdownfeld, und klicken Sie dann auf **dieses Schema verwenden**.  
  
     Die Schemadefinitionsdatei ist nun der DBML- oder XML-Zuordnungsdatei zugeordnet.  
  
     Stellen Sie sicher, dass keine anderen Schemadefinitionen ausgewählt werden.  
  
7.  Auf der **Ansicht** Menü klicken Sie auf **Fehlerliste**.  
  
     Ermitteln Sie, ob Fehler, Warnungen oder Meldungen erzeugt wurden. Ist dies nicht der Fall, ist die XML-Datei für die Schemadefinition gültig.  
  
## <a name="alternate-method-for-supplying-schema-definition"></a>Alternative Methode zur Bereitstellung einer Schemadefinition  
 Wenn aus irgendeinem Grund die passende .xsd Datei nicht in angezeigt wird der **XML-Schemas** (Dialogfeld), können Sie die XSD-Datei aus einem Hilfethema herunterladen. Die folgenden Schritte unterstützen Sie beim Speichern der heruntergeladenen Datei im Unicode-Format des [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]-XML-Editors.  
  
#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a>So kopieren Sie eine Schemadefinitionsdatei aus einem Hilfethema  
  
1.  Suchen Sie das Hilfethema, das die Schemadefinition enthält (siehe weiter oben in diesem Abschnitt).  
  
    -   DBML-Dateien finden Sie unter [Codegenerierung in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
    -   Externe Zuordnungsdateien finden Sie unter [externe Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
2.  Klicken Sie auf **Code kopieren** auf die Codedatei in die Zwischenablage zu kopieren.  
  
3.  Starten Sie Editor, um eine neue Datei zu erstellen.  
  
4.  Fügen Sie den Code aus der Zwischenablage in die Editor-Datei ein.  
  
5.  Klicken Sie im Editor **Datei** Menü klicken Sie auf **speichern unter**.  
  
6.  In der **Codierung** wählen Sie im **Unicode**.  
  
    > [!IMPORTANT]
    >  Diese Auswahl stellt sicher, dass die Unicode-16-Byte-Sortierungsmarkierung (`FFFE`) der Textdatei vorangestellt wird.  
  
7.  In der **Dateiname** Feld, erstellen Sie einen Dateinamen mit der Erweiterung XSD.  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
