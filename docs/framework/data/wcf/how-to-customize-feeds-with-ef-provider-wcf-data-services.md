---
title: "Gewusst wie: Anpassen von Feeds mit dem Entity Framework-Anbieter (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF Data Services, Anpassen"
  - "WCF Data Services, Anpassen von Feeds"
ms.assetid: fd16272e-36f2-415e-850e-8a81f2b17525
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Gewusst wie: Anpassen von Feeds mit dem Entity Framework-Anbieter (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ermöglicht es Ihnen, die Atom\-Serialisierung in einer Datendienstantwort anzupassen, damit Eigenschaften einer Entität nicht verwendeten Elementen zugeordnet werden können, die im AtomPub\-Protokoll definiert werden.  In diesem Thema wird gezeigt, wie Zuordnungsattribute für die Entitätstypen in einem Datenmodell definiert werden, das in einer EDMX\-Datei mit dem Entity Framework\-Anbieter definiert wird.  Weitere Informationen finden Sie unter [Feedanpassung](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).  
  
 In diesem Thema ändern Sie die Tool\-generierte EDMX\-Datei, die das Datenmodell enthält, manuell.  Sie müssen die Datei manuell ändern, da Erweiterungen des Datenmodells nicht vom Entity Designer unterstützt werden.  Weitere Informationen zur von den Entity Data Model\-Tools generierten EDMX\-Datei finden Sie unter [.edmx File Overview](http://msdn.microsoft.com/de-de/f4c8e7ce-1db6-417e-9759-15f8b55155d4).  Im Beispiel in diesem Thema werden der Northwind\-Beispieldatendienst und automatisch generierte Client\-Datendienstklassen verwendet.  Dieser Dienst und die Clientdatenklassen werden erstellt, wenn Sie den [WCF Data Services\-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) ausführen.  
  
### So ändern Sie manuell die Datei Northwind.edmx, um Feedanpassungsattribute hinzuzufügen  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf die Datei `Northwind.edmx`, und klicken Sie dann auf **Öffnen mit**.  
  
2.  Wählen Sie im Dialogfeld **Öffnen mit \- Northwind.edmx** die Option **XML\-Editor** aus, und klicken Sie dann auf **OK**.  
  
3.  Suchen Sie das `ConceptualModels`\-Element, und ersetzen Sie den vorhandenen `Customers`\-Entitätstyp durch das folgende Element, das Feedanpassungszuordnungsattribute enthält:  
  
     [!code-xml[Astoria Custom Feeds#EdmFeedCustomers](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/northwind.csdl#edmfeedcustomers)]  
  
4.  Speichern Sie die Änderungen, und schließen Sie die Datei Northwind.edmx.  
  
5.  \(Optional\) Klicken Sie mit der rechten Maustaste auf die Datei Northwind.edmx, und klicken Sie dann auf **Benutzerdefiniertes Tool ausführen**.  
  
     Hierdurch wird die Objektebenendatei erneut erstellt, was möglicherweise erforderlich ist.  
  
6.  Kompilieren Sie das Projekt neu.  
  
## Beispiel  
 Das vorherige Beispiel gibt das folgende Ergebnis für den URI `http://myservice/` `Northwind.svc/Customers('ALFKI')` zurück.  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedResult](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/edmfeedresult.xml#edmfeedresult)]  
  
## Siehe auch  
 [Entity Framework\-Anbieter](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)