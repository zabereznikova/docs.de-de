---
title: "Gewusst wie: Abfangen von Datendienstnachrichten (WCF Data Services) | Microsoft Docs"
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
  - "Abfrageinterceptoren (WCF Data Services)"
  - "WCF Data Services, Anpassen"
ms.assetid: 24b9df1b-b54b-4795-a033-edf333675de6
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Gewusst wie: Abfangen von Datendienstnachrichten (WCF Data Services)
Mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] können Sie Anforderungsnachrichten abfangen, damit Sie einem Vorgang benutzerdefinierte Logik hinzufügen können.  Zum Abfangen einer Nachricht verwenden Sie besonders attributierte Methoden im Datendienst.  Weitere Informationen finden Sie unter [Interceptoren](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md).  
  
 In dem Beispiel in diesem Thema wird der Northwind\-Beispieldatendienst verwendet.  Dieser Dienst wird erstellt, wenn Sie den [WCF Data Services\-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) ausführen.  
  
### So definieren Sie einen Abfrage\-Interceptor für die "Orders"\-Entitätenmenge  
  
1.  Öffnen Sie im Northwind\-Datendienstprojekt die Datei Northwind.svc.  
  
2.  Fügen Sie der Codepage für die `Northwind`\-Klasse die folgende `using`\-Anweisung hinzu \(`Imports` in Visual Basic\).  
  
     [!code-csharp[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#usinglinqexpressions)]
     [!code-vb[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#usinglinqexpressions)]  
  
3.  Definieren Sie in der `Northwind`\-Klasse eine Dienstvorgangsmethode mit dem Namen `OnQueryOrders` wie folgt:  
  
     [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptordef)]
     [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
### So definieren Sie einen Change\-Interceptor für die "Products"\-Entitätenmenge  
  
1.  Öffnen Sie im Northwind\-Datendienstprojekt die Datei Northwind.svc.  
  
2.  Definieren Sie in der `Northwind`\-Klasse eine Dienstvorgangsmethode mit dem Namen `OnChangeProducts` wie folgt:  
  
     [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptordef)]
     [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
## Beispiel  
 In diesem Beispiel wird eine Abfrage\-Interceptor\-Methode für die `Orders`\-Entitätenmenge definiert, die einen Lambda\-Ausdruck zurückgibt.  Dieser Ausdruck enthält einen Delegaten, der die angeforderten `Orders` auf Grundlage verknüpfter `Customers` filtert, die einen bestimmten Kontaktnamen haben.  Der Name wird wiederum auf Grundlage des anfordernden Benutzers bestimmt.  In diesem Beispiel wird davon ausgegangen, dass der Datendienst innerhalb einer ASP.NET\-Webanwendung gehostet wird, die WCF verwendet, und dass die Authentifizierung aktiviert ist.  Die <xref:System.Web.HttpContext>\-Klasse wird verwendet, um das Prinzip der aktuellen Anforderung abzurufen.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptor)]
 [!code-vb[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptor)]  
  
## Beispiel  
 In diesem Beispiel wird eine Change\-Interceptor\-Methode für die `Products`\-Entitätenmenge definiert.  Diese Methode überprüft die Eingabe an den Dienst für einen <xref:System.Data.Services.UpdateOperations>\-Vorgang oder <xref:System.Data.Services.UpdateOperations>\-Vorgang und löst eine Ausnahme aus, wenn eine Änderung an einem ausgelaufenen Produkt vorgenommen wird.  Sie blockiert außerdem das Löschen von Produkten als nicht unterstützten Vorgang.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptor)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptor)]  
  
## Siehe auch  
 [Gewusst wie: Definieren eines Dienstvorgangs](../../../../docs/framework/data/wcf/how-to-define-a-service-operation-wcf-data-services.md)   
 [Definieren von WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)