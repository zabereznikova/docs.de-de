---
title: "Gewusst wie: Hinzuf&#252;gen eines Datendienstverweises (WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, Konfigurieren"
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Gewusst wie: Hinzuf&#252;gen eines Datendienstverweises (WCF Data Services)
Sie können über das Dialogfeld **Dienstverweis hinzufügen** in Visual Studio einen Verweis auf [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] hinzufügen.  Dies erleichtert Ihnen den Zugriff auf einen Datendienst in einer Clientanwendung, den Sie in Visual Studio entwickeln.  Wenn Sie diese Prozedur ausführen, werden Datenklassen auf Grundlage von aus dem Datendienst abgerufenen Metadaten generiert.  Weitere Informationen finden Sie unter [Generieren der Datendienst\-Clientbibliothek](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).  
  
### So fügen Sie einen Datendienstverweis hinzu  
  
1.  \(Optional\) Wenn der Datendienst kein Teil der Projektmappe ist und nicht bereits ausgeführt ist, starten Sie den Datendienst und notieren Sie den URI des Datendiensts.  
  
2.  Klicken Sie mit der rechten Maustaste auf das Clientprojekt, und wählen Sie **Dienstverweis hinzufügen** aus.  
  
3.  Klicken Sie auf **Ermitteln**, wenn der Datendienst Teil der aktuellen Projektmappe ist.  
  
     \- oder \-  
  
     Geben Sie im Textfeld **Adresse** die Basis\-URL des Datendiensts ein, z. B. `http://localhost:1234/Northwind.svc`, und klicken Sie dann auf **Gehe zu**.  
  
4.  Klicken Sie auf **OK**.  
  
     Dadurch wird eine neue Codedatei hinzugefügt, die die zum Zugriff auf und zur Interaktion mit Datendienstressourcen als Objekte \+verwendeten Datenklassen enthält.  
  
## Siehe auch  
 [Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)