---
title: "Arbeiten mit der Datendefinitionssprache | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Arbeiten mit der Datendefinitionssprache
Ab Version 4 von [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] unterstützt [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] DDL \(Datendefinitionssprache\).  Dadurch wird das Erstellen oder Löschen einer Datenbankinstanz auf Grundlage der Verbindungszeichenfolge und der Metadaten des Speichermodells \(SSDL\) ermöglicht.  
  
 Die folgenden Methoden für den <xref:System.Data.Objects.ObjectContext> verwenden die Verbindungszeichenfolge und den SSDL\-Inhalt, um Folgendes durchzuführen: Erstellen oder Löschen der Datenbank, Überprüfen, ob die Datenbank vorhanden ist, und Anzeigen des generierten DDL\-Skripts:  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
>  Beim Ausführen der DDL\-Befehle wird von ausreichenden Berechtigungen ausgegangen.  
  
 Die oben aufgeführten Methoden delegieren die meiste Arbeit an den zugrunde liegenden ADO.NET\-Datenanbieter.  Der Anbieter ist dafür verantwortlich, dass die zum Generieren von Datenbankobjekten verwendete Namenskonvention mit den zur Abfrage und Aktualisierung verwendeten Konventionen konsistent ist.  
  
 Im folgenden Beispiel wird dargestellt, wie die Datenbank auf Grundlage des vorhandenen Modells generiert wird.  Außerdem wird ein neues Entitätsobjekt dem Objektkontext hinzugefügt und in der Datenbank gespeichert.  
  
## Verfahren  
  
#### So definieren Sie eine Datenbank auf Grundlage des vorhandenen Modells  
  
1.  Erstellen Sie eine Konsolenanwendung.  
  
2.  Fügen Sie der Anwendung ein vorhandenes Modell hinzu.  
  
    1.  Fügen Sie ein leeres Modell mit dem Namen `SchoolModel` hinzu.  Informationen zur Erstellung eines leeren Modells finden Sie im Thema [How to: Create a New .edmx File](http://msdn.microsoft.com/de-de/beb8189e-e51c-4051-839c-9902c224abf2).  
  
     Die Datei **SchoolModel.edmx** wird dem Projekt hinzugefügt.  
  
    1.  Kopieren Sie den konzeptionellen Inhalt, den Speicherinhalt und den Zuordnungsinhalt für das Modell "School" aus dem Thema [School Model](http://msdn.microsoft.com/de-de/859a9587-81ea-4a45-9bc0-f8d330e1adac).  
  
    2.  Öffnen Sie die Datei **SchoolModel.edmx**, und fügen Sie den Inhalt zwischen den `edmx:Runtime`\-Tags ein.  
  
3.  Fügen Sie der Hauptfunktion den folgenden Code hinzu.  Im Code werden die Verbindungszeichenfolge mit dem Datenbankserver initialisiert, das DDL\-Skript angezeigt, die Datenbank erstellt, dem Kontext eine neue Entität hinzugefügt und die Änderungen in der Datenbank gespeichert.  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]