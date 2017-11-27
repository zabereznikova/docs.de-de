---
title: Benutzerdefinierte Nachrichtenformatierung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c07435f3-5214-4791-8961-2c2b61306d71
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 01998d0ac732f63f6771c47bfc76a8207a5531f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="custom-message-formatters"></a>Benutzerdefinierte Nachrichtenformatierung
Der Inhalt einer Nachricht weist häufig das XML-Format auf, also kein gängiges Format für eine Anwendung. Anwendungen bearbeiten Objekte, indem sie ihre Eigenschaften abrufen und festlegen. [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]verwendet die *Datenvertrag* Konvertieren einer <xref:System.ServiceModel.Channels.Message> Objekt in ein Objekt, das von einer Anwendung problemlos bewältigt. Diese Prozesse werden als Serialisierung und Deserialisierung bezeichnet. Beachten Sie, dass diese Begriffe auch verwendet werden, um die Serialisierung und Deserialisierung einer Transportebene in das bzw. aus dem Nachrichtensendeformat zu beschreiben. Dabei handelt es sich um einen nicht verwandten Prozess.  
  
 Sie können eine benutzerdefinierte Nachrichtenformatierung verwenden, wenn Sie eine spezielle Konvertierung zwischen Nachrichten und Objekten implementieren müssen, die Sie mithilfe eines Datenvertrags nicht durchführen können. Ändern bzw. erweitern Sie dazu das Ausführungsverhalten eines bestimmten Vertragsvorgangs auf einem Client oder für einen Dienst.  
  
## <a name="custom-message-formatters-on-the-client"></a>Benutzerdefinierte Nachrichtenformatierungen auf dem Client  
 Die <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>-Schnittstelle definiert Methoden, die verwendet werden, um für Clientanwendungen die Konvertierung von Nachrichten in Objekte und von Objekten in Nachrichten zu steuern.  
  
 Sie müssen diese Schnittstelle implementieren. Überschreiben Sie zuerst die <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.DeserializeReply%2A>-Methode, um eine Nachricht zu deserialisieren. Diese Methode wird aufgerufen, nachdem eine eingehende Nachricht empfangen wurde, aber bevor sie an den Clientvorgang gesendet wurde.  
  
 Überschreiben Sie im nächsten Schritt die <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.SerializeRequest%2A>-Methode, um ein Objekt zu serialisieren. Diese Methode wird vor dem Senden einer ausgehenden Nachricht aufgerufen.  
  
 Um die benutzerdefinierte Formatierung in die Dienstanwendung einzufügen, müssen Sie das <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>-Objekt der <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A>-Eigenschaft zuweisen, indem Sie ein Vorgangsverhalten verwenden. Informationen zum Verhalten finden Sie unter [konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="custom-message-formatters-on-the-service"></a>Benutzerdefinierte Nachrichtenformatierungen für den Dienst  
 Die <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>-Schnittstelle definiert Methoden, die ein <xref:System.ServiceModel.Channels.Message>-Objekt in Parameter für einen Vorgang bzw. aus Parametern in ein <xref:System.ServiceModel.Channels.Message>-Objekt in einer Dienstanwendung konvertieren.  
  
 Sie müssen diese Schnittstelle implementieren. Überschreiben Sie zuerst die <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.DeserializeReply%2A>-Methode, um eine Nachricht zu deserialisieren. Diese Methode wird aufgerufen, nachdem eine eingehende Nachricht empfangen wurde, aber bevor sie an den Clientvorgang gesendet wurde.  
  
 Überschreiben Sie im nächsten Schritt die <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.SerializeRequest%2A>-Methode, um ein Objekt zu serialisieren. Diese Methode wird vor dem Senden einer ausgehenden Nachricht aufgerufen.  
  
 Um die benutzerdefinierte Formatierung in die Dienstanwendung einzufügen, müssen Sie das <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>-Objekt der <xref:System.ServiceModel.Dispatcher.DispatchOperation.Formatter%2A>-Eigenschaft zuweisen, indem Sie ein Vorgangsverhalten verwenden. Informationen zum Verhalten finden Sie unter [konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>  
 <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>  
 [Konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
