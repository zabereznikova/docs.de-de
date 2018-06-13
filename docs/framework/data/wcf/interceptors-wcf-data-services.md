---
title: Interceptors (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: e33ae8dc-8069-41d0-99a0-75ff28db7050
ms.openlocfilehash: f3ff08dd4cd20e7ce226750a386cfddb27731923
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33363799"
---
# <a name="interceptors-wcf-data-services"></a>Interceptors (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ermöglicht einer Anwendung zum Abfangen von Anforderungsnachrichten, damit Sie einen Vorgang benutzerdefinierten Logik hinzufügen können. Sie können diese benutzerdefinierten Logik zum Überprüfen der Daten in eingehenden Nachrichten verwenden. Sie können damit außerdem den Bereich einer Abfrageanforderung weiter einschränken, z. B. um eine benutzerdefinierte Autorisierungsrichtlinie für jede Anforderung einzufügen.  
  
 Das Abfangen wird von speziell attributierten Methoden im Datendienst ausgeführt. Diese Methoden werden von [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] zum entsprechenden Zeitpunkt während der Nachrichtenverarbeitung aufgerufen. Interceptors werden regelmäßig Satz pro Entität definiert, und interceptormethoden können keine Parameter in der Anforderung nicht annehmen, wie Dienstvorgänge können. Abfrage-Interceptor-Methoden, die beim Verarbeiten einer HTTP GET-Anforderung aufgerufen werden, müssen zurückgeben, ein Lambda-Ausdruck, der bestimmt, ob eine Instanz des Interceptors Entität festgelegt, die von den Abfrageergebnissen zurückgegeben werden soll. Dieser Ausdruck wird vom Datendienst verwendet, um den angeforderten Vorgang weiter zu optimieren. Nachfolgend wird eine Beispieldefinition eines Abfrage-Interceptors dargestellt.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 Weitere Informationen finden Sie unter [wie: Abfangen von Datendienstnachrichten](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
 Change-Interceptoren, die beim Verarbeiten von Nicht-Abfragevorgängen aufgerufen werden, müssen `void` (`Nothing` in Visual Basic) zurückgeben. Change-Interceptor-Methoden müssen die folgenden beiden Parameter akzeptieren:  
  
1.  Ein Parameter eines Typs, der mit dem Entitätstyp der Entitätenmenge kompatibel ist. Wenn der Datendienst den Change-Interceptor aufruft, spiegelt der Wert dieses Parameters die von der Anforderung gesendeten Entitätsinformationen wider.  
  
2.  Ein Parameter vom Typ <xref:System.Data.Services.UpdateOperations>. Wenn der Datendienst den Change-Interceptor aufruft, spiegelt der Wert dieses Parameters den Vorgang wider, den die Anforderung auszuführen versucht.  
  
 Nachfolgend wird eine Beispieldefinition eines Change-Interceptors dargestellt.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 Weitere Informationen finden Sie unter [wie: Abfangen von Datendienstnachrichten](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
 Die folgenden Attribute werden für das Abfangen unterstützt.  
  
 **[QueryInterceptor (** *EnitySetName* **)]**  
 Methoden mit angewendetem <xref:System.Data.Services.QueryInterceptorAttribute>-Attribut werden aufgerufen, wenn eine HTTP GET-Anforderung für die Ziel-Entitätenmengenressource empfangen wird. Diese Methoden müssen immer einen Lambda-Ausdruck in Form von `Expression<Func<T,bool>>` zurückgeben.  
  
 **[ChangeInterceptor (** *EnitySetName* **)]**  
 Methoden mit angewendetem <xref:System.Data.Services.ChangeInterceptorAttribute>-Attribut werden aufgerufen, wenn eine andere HTTP-Anforderung als eine HTTP GET-Anforderung für die Ziel-Entitätenmengenressource empfangen wird. Diese Methoden müssen immer `void` (`Nothing` in Visual Basic) zurückgeben.  
  
 Weitere Informationen finden Sie unter [wie: Abfangen von Datendienstnachrichten](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Dienstvorgänge](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)
