---
title: Benutzerdefinierte Nachrichtenformatierung
ms.date: 03/30/2017
ms.assetid: c07435f3-5214-4791-8961-2c2b61306d71
ms.openlocfilehash: e238eb134772c0a95934a460edda62ca9dba2518
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254752"
---
# <a name="custom-message-formatters"></a>Benutzerdefinierte Nachrichtenformatierung

Der Inhalt einer Nachricht weist häufig das XML-Format auf, also kein gängiges Format für eine Anwendung. Anwendungen bearbeiten Objekte, indem sie ihre Eigenschaften abrufen und festlegen. Windows Communication Foundation (WCF) verwendet den *Datenvertrag* , um ein-Objekt in ein Objekt zu konvertieren, das <xref:System.ServiceModel.Channels.Message> von einer Anwendung problemlos behandelt werden soll. Diese Prozesse werden als Serialisierung und Deserialisierung bezeichnet. Beachten Sie, dass diese Begriffe auch verwendet werden, um die Serialisierung und Deserialisierung einer Transportebene in das bzw. aus dem Nachrichtensendeformat zu beschreiben. Dabei handelt es sich um einen nicht verwandten Prozess.  
  
 Sie können eine benutzerdefinierte Nachrichtenformatierung verwenden, wenn Sie eine spezielle Konvertierung zwischen Nachrichten und Objekten implementieren müssen, die Sie mithilfe eines Datenvertrags nicht durchführen können. Ändern bzw. erweitern Sie dazu das Ausführungsverhalten eines bestimmten Vertragsvorgangs auf einem Client oder für einen Dienst.  
  
## <a name="custom-message-formatters-on-the-client"></a>Benutzerdefinierte Nachrichtenformatierungen auf dem Client  

 Die <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>-Schnittstelle definiert Methoden, die verwendet werden, um für Clientanwendungen die Konvertierung von Nachrichten in Objekte und von Objekten in Nachrichten zu steuern.  
  
 Sie müssen diese Schnittstelle implementieren. Überschreiben Sie zuerst die <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.DeserializeReply%2A>-Methode, um eine Nachricht zu deserialisieren. Diese Methode wird aufgerufen, nachdem eine eingehende Nachricht empfangen wurde, aber bevor sie an den Clientvorgang gesendet wurde.  
  
 Überschreiben Sie im nächsten Schritt die <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.SerializeRequest%2A>-Methode, um ein Objekt zu serialisieren. Diese Methode wird vor dem Senden einer ausgehenden Nachricht aufgerufen.  
  
 Um die benutzerdefinierte Formatierung in die Dienstanwendung einzufügen, müssen Sie das <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>-Objekt der <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A>-Eigenschaft zuweisen, indem Sie ein Vorgangsverhalten verwenden. Weitere Informationen zu Verhalten finden Sie unter [Konfigurieren und Erweitern der Laufzeit mit Verhalten](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="custom-message-formatters-on-the-service"></a>Benutzerdefinierte Nachrichtenformatierungen für den Dienst  

 Die <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>-Schnittstelle definiert Methoden, die ein <xref:System.ServiceModel.Channels.Message>-Objekt in Parameter für einen Vorgang bzw. aus Parametern in ein <xref:System.ServiceModel.Channels.Message>-Objekt in einer Dienstanwendung konvertieren.  
  
 Sie müssen diese Schnittstelle implementieren. Überschreiben Sie zuerst die <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.DeserializeReply%2A>-Methode, um eine Nachricht zu deserialisieren. Diese Methode wird aufgerufen, nachdem eine eingehende Nachricht empfangen wurde, aber bevor sie an den Clientvorgang gesendet wurde.  
  
 Überschreiben Sie im nächsten Schritt die <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.SerializeRequest%2A>-Methode, um ein Objekt zu serialisieren. Diese Methode wird vor dem Senden einer ausgehenden Nachricht aufgerufen.  
  
 Um die benutzerdefinierte Formatierung in die Dienstanwendung einzufügen, müssen Sie das <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>-Objekt der <xref:System.ServiceModel.Dispatcher.DispatchOperation.Formatter%2A>-Eigenschaft zuweisen, indem Sie ein Vorgangsverhalten verwenden. Weitere Informationen zu Verhalten finden Sie unter [Konfigurieren und Erweitern der Laufzeit mit Verhalten](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>
- [Konfigurieren und Erweitern der Laufzeit mit Verhalten](configuring-and-extending-the-runtime-with-behaviors.md)
