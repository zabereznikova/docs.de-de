---
title: "Vorgehensweise: Validierung von DBML und externen Zuordnungsdateien | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Validierung von DBML und externen Zuordnungsdateien
Externe Zuordnungsdateien und von Ihnen geänderte .dbml\-Dateien müssen hinsichtlich ihrer jeweiligen Schemadefinitionen überprüft werden.  Dieser Abschnitt bietet [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]\-Benutzern Informationen zu den Schritten für das Implementieren des Validierungsprozesses.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
### So validieren Sie ein .dbml\- oder eine XML\-Datei  
  
1.  Zeigen Sie im Visual Studio\-Menü **Datei** auf **Öffnen**, und klicken Sie dann auf **Datei**.  
  
2.  Klicken Sie im Dialogfeld **Datei öffnen** auf die zu validierende .dbml\- oder XML\-Zuordnungsdatei.  
  
     Die Datei wird im **XML\-Editor** geöffnet.  
  
3.  Klicken Sie mit der rechten Maustaste auf das Fenster, und klicken Sie dann auf **Eigenschaften**.  
  
4.  Klicken Sie im Fenster **Eigenschaften** in der **Schemata**\-Eigenschaft auf die Auslassungspunkte \(...\).  
  
     Das Dialogfeld **XML\-Schemata** wird geöffnet.  
  
5.  Beachten Sie die entsprechende Schemadefinition für den Zweck.  
  
    -   DbmlSchema.xsd ist die Schemadefinition zum Validieren einer .dbml\-Datei.  Weitere Informationen finden Sie unter [Codegenerierung in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
    -   LinqToSqlMapping.xsd ist die Schemadefinition zum Überprüfen einer externen XML\-Zuordnungsdatei.  Weitere Informationen finden Sie unter [Externe Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
6.  Klicken Sie in die Spalte **Verwenden** der gewünschten Zeile in der Schemadefinition, um das Listenfeld zu öffnen. Klicken Sie dann auf **Dieses Schema verwenden**.  
  
     Die Schemadefinitionsdatei ist nun der DBML\- oder XML\-Zuordnungsdatei zugeordnet.  
  
     Stellen Sie sicher, dass keine anderen Schemadefinitionen ausgewählt werden.  
  
7.  Klicken Sie im Menü **Ansicht** auf **Fehlerliste**.  
  
     Ermitteln Sie, ob Fehler, Warnungen oder Meldungen erzeugt wurden.  Ist dies nicht der Fall, ist die XML\-Datei für die Schemadefinition gültig.  
  
## Alternative Methode zur Bereitstellung einer Schemadefinition  
 Erscheint die passende .xsd\-Datei aus irgendeinem Grund nicht im Dialogfeld **XML\-Schemata**, können Sie die xsd\-Datei aus einem Hilfethema herunterladen.  Die folgenden Schritte unterstützen Sie beim Speichern der heruntergeladenen Datei im Unicode\-Format des [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]\-XML\-Editors.  
  
#### So kopieren Sie eine Schemadefinitionsdatei aus einem Hilfethema  
  
1.  Suchen Sie das Hilfethema, das die Schemadefinition enthält \(siehe weiter oben in diesem Abschnitt\).  
  
    -   .dbml\-Dateien finden Sie unter [Codegenerierung in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
    -   Externe Zuordnungsdateien finden Sie unter [Externe Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
2.  Klicken Sie auf **Code kopieren**, um die Codedatei in die Zwischenablage zu kopieren.  
  
3.  Starten Sie Editor, um eine neue Datei zu erstellen.  
  
4.  Fügen Sie den Code aus der Zwischenablage in die Editor\-Datei ein.  
  
5.  Klicken Sie im Editor\-Menü **Datei** auf **Speichern unter**.  
  
6.  Wählen Sie im Feld **Codierung** **Unicode** aus.  
  
    > [!IMPORTANT]
    >  Diese Auswahl stellt sicher, dass die Unicode\-16\-Byte\-Sortierungsmarkierung \(`FFFE`\) der Textdatei vorangestellt wird.  
  
7.  Geben Sie im Feld **Dateiname** einen Dateinamen mit einer Erweiterung .xsd ein.  
  
## Siehe auch  
 [Verweis](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)