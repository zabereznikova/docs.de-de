---
title: Arbeiten mit der Datendefinitionssprache
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8b363105f0dd6978d4e59678fb7cd1b3f1d721df
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="working-with-data-definition-language"></a>Arbeiten mit der Datendefinitionssprache
Beginnend mit der [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] Version 4 der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Datendefinitionssprache (DDL) unterstützt. Dadurch wird das Erstellen oder Löschen einer Datenbankinstanz auf Grundlage der Verbindungszeichenfolge und der Metadaten des Speichermodells (SSDL) ermöglicht.  
  
 Die folgenden Methoden für den <xref:System.Data.Objects.ObjectContext> verwenden die Verbindungszeichenfolge und den SSDL-Inhalt, um Folgendes durchzuführen: Erstellen oder Löschen der Datenbank, Überprüfen, ob die Datenbank vorhanden ist, und Anzeigen des generierten DDL-Skripts:  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
>  Beim Ausführen der DDL-Befehle wird von ausreichenden Berechtigungen ausgegangen.  
  
 Die oben aufgeführten Methoden delegieren die meiste Arbeit an den zugrunde liegenden ADO.NET-Datenanbieter. Der Anbieter ist dafür verantwortlich, dass die zum Generieren von Datenbankobjekten verwendete Namenskonvention mit den zur Abfrage und Aktualisierung verwendeten Konventionen konsistent ist.  
  
 Im folgenden Beispiel wird dargestellt, wie die Datenbank auf Grundlage des vorhandenen Modells generiert wird. Außerdem wird ein neues Entitätsobjekt dem Objektkontext hinzugefügt und in der Datenbank gespeichert.  
  
## <a name="procedures"></a>Verfahren  
  
#### <a name="to-define-a-database-based-on-the-existing-model"></a>So definieren Sie eine Datenbank auf Grundlage des vorhandenen Modells  
  
1.  Erstellen Sie eine Konsolenanwendung.  
  
2.  Fügen Sie der Anwendung ein vorhandenes Modell hinzu.  
  
    1.  Fügen Sie ein leeres Modell mit dem Namen `SchoolModel`. Um ein leeres Modell erstellen, finden Sie unter der [Vorgehensweise: Erstellen Sie eine neue EDMX-Datei](http://msdn.microsoft.com/en-us/beb8189e-e51c-4051-839c-9902c224abf2) Thema.  
  
     Die Datei SchoolModel.edmx wird dem Projekt hinzugefügt.  
  
    1.  Kopieren Sie den konzeptionellen, Speicher und Zuordnen von Inhalt für das Modell "School" aus der [Modell ' School '](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac) Thema.  
  
    2.  Öffnen Sie die Datei SchoolModel.edmx`edmx:Runtime`, und fügen Sie den Inhalt zwischen den -Tags ein.  
  
3.  Fügen Sie der Hauptfunktion den folgenden Code hinzu. Im Code werden die Verbindungszeichenfolge mit dem Datenbankserver initialisiert, das DDL-Skript angezeigt, die Datenbank erstellt, dem Kontext eine neue Entität hinzugefügt und die Änderungen in der Datenbank gespeichert.  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]
