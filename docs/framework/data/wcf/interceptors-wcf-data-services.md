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
ms.openlocfilehash: c9799037ae0ea8b29b5e989859aff29c310593d4
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568971"
---
# <a name="interceptors-wcf-data-services"></a>Interceptors (WCF Data Services)
WCF Data Services ermöglicht einer Anwendung das Abfangen von Anforderungs Nachrichten, damit Sie einem Vorgang benutzerdefinierte Logik hinzufügen können. Sie können diese benutzerdefinierte Logik verwenden, um Daten in eingehenden Nachrichten zu validieren. Sie können damit außerdem den Bereich einer Abfrageanforderung weiter einschränken, z. B. um eine benutzerdefinierte Autorisierungsrichtlinie für jede Anforderung einzufügen.  
  
 Das Abfangen wird von speziell attributierten Methoden im Datendienst ausgeführt. Diese Methoden werden von WCF Data Services an der entsprechenden Stelle der Nachrichtenverarbeitung aufgerufen. Interceptors werden pro Entitätenmenge definiert, und Interceptor Methoden können keine Parameter aus der Anforderung annehmen, wie dies bei Dienst Vorgängen möglich ist. Abfrage-Interceptor-Methoden, die beim Verarbeiten einer HTTP GET-Anforderung aufgerufen werden, müssen einen Lambda Ausdruck zurückgeben, der bestimmt, ob eine Instanz der Entitätenmenge des Interceptors von den Abfrage Ergebnissen zurückgegeben werden soll. Dieser Ausdruck wird vom Datendienst verwendet, um den angeforderten Vorgang weiter zu optimieren. Nachfolgend wird eine Beispieldefinition eines Abfrage-Interceptors dargestellt.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 Weitere Informationen finden Sie unter Gewusst [wie: Abfangen von Datendienst Nachrichten](how-to-intercept-data-service-messages-wcf-data-services.md).  
  
 Change-Interceptoren, die beim Verarbeiten von Nicht-Abfragevorgängen aufgerufen werden, müssen `void` (`Nothing` in Visual Basic) zurückgeben. Change-Interceptor-Methoden müssen die folgenden beiden Parameter akzeptieren:  
  
1. Ein Parameter eines Typs, der mit dem Entitätstyp der Entitätenmenge kompatibel ist. Wenn der Datendienst den Change-Interceptor aufruft, spiegelt der Wert dieses Parameters die von der Anforderung gesendeten Entitätsinformationen wider.  
  
2. Ein Parameter vom Typ <xref:System.Data.Services.UpdateOperations>. Wenn der Datendienst den Change-Interceptor aufruft, spiegelt der Wert dieses Parameters den Vorgang wider, den die Anforderung auszuführen versucht.  
  
 Nachfolgend wird eine Beispieldefinition eines Change-Interceptors dargestellt.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 Weitere Informationen finden Sie unter Gewusst [wie: Abfangen von Datendienst Nachrichten](how-to-intercept-data-service-messages-wcf-data-services.md).  
  
 Die folgenden Attribute werden für das Abfangen unterstützt.  
  
 **[Queryinterceptor (** *entitySetName* **)]**  
 Methoden mit angewendetem <xref:System.Data.Services.QueryInterceptorAttribute>-Attribut werden aufgerufen, wenn eine HTTP GET-Anforderung für die Ziel-Entitätenmengenressource empfangen wird. Diese Methoden müssen immer einen Lambdaausdruck in Form von `Expression<Func<T,bool>>` zurückgeben.  
  
 **[Changeinterceptor (** *entitySetName* **)]**  
 Methoden mit angewendetem <xref:System.Data.Services.ChangeInterceptorAttribute>-Attribut werden aufgerufen, wenn eine andere HTTP-Anforderung als eine HTTP GET-Anforderung für die Ziel-Entitätenmengenressource empfangen wird. Diese Methoden müssen immer `void` (`Nothing` in Visual Basic) zurückgeben.  
  
 Weitere Informationen finden Sie unter Gewusst [wie: Abfangen von Datendienst Nachrichten](how-to-intercept-data-service-messages-wcf-data-services.md).  
  
## <a name="see-also"></a>Siehe auch

- [Dienstvorgänge](service-operations-wcf-data-services.md)
