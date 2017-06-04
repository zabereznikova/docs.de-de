---
title: "Lernprogramm &#39;Erste Schritte&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Erste Schritte [WCF]"
  - "WCF [WCF], Erste Schritte"
  - "Windows Communication Foundation [WCF], Erste Schritte"
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
caps.latest.revision: 47
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 47
---
# Lernprogramm &#39;Erste Schritte&#39;
Die in diesem Abschnitt enthaltenen Themen sollen Ihnen einen schnellen Überblick über das Programmieren mit [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] geben.  Die Liste am Ende dieses Themas gibt Aufschluss über die Reihenfolge, in der die Aufgaben ausgeführt werden müssen.  Wenn Sie dieses Lernprogramm absolviert haben, verfügen Sie über ein grundlegendes Verständnis der zur Erstellung von Dienst\- und Clientanwendungen mit [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] notwendigen Schritte.  Ein Dienst macht einen oder mehrere Endpunkte verfügbar, von denen jeder wiederum einen oder mehrere Dienstvorgänge zur Verfügung stellt.  Der *Endpunkt* eines Diensts gibt die Adresse an, unter der der Dienst zu finden ist, eine Bindung, die die Informationen zur Kommunikation des Clients mit dem Dienst enthält, sowie einen Vertrag, der die Funktionalität definiert, die der Dienst seinen Clients zur Verfügung stellt.  
  
 Nachdem Sie die Themenfolge dieses Lernprogramms durchgearbeitet haben, verfügen Sie über einen funktionierenden Dienst und über einen Client, der den Dienst aufrufen kann.  Die ersten drei Themen beschreiben, wie ein Dienstvertrag definiert und implementiert und wie der Dienst gehostet wird.  Der erstellte Dienst ist innerhalb einer Konsolenanwendung selbst gehostet.  Dienste können auch unter IIS \(Internetinformationsdienste\) gehostet werden.  [!INCLUDE[crabout](../../../includes/crabout-md.md)] zu dieser Vorgehensweise finden Sie unter [Gewusst wie: Hosten eines WCF\-Diensts in IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  Der Dienst wird im Code konfiguriert. Dienste können jedoch auch in einer Konfigurationsdatei konfiguriert werden.  [!INCLUDE[crabout](../../../includes/crabout-md.md)] die Verwendung einer Konfigurationsdatei finden Sie unter [Konfigurieren von Diensten mit Konfigurationsdateien](../../../docs/framework/wcf/configuring-services-using-configuration-files.md).  
  
 In den nächsten drei Themen wird beschrieben, wie ein Clientproxy erstellt, die Clientanwendung konfiguriert und der Clientproxy verwendet wird, um einen Dienstvorgang aufzurufen, der vom Dienst verfügbar gemacht wird.  Dienste veröffentlichen Metadaten, die die Informationen definieren, über die eine Clientanwendung mit dem Dienst kommuniziert.  [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] automatisiert den Zugriff auf diese Metadaten und verwendet sie, um die Clientanwendung für den Dienst zu erstellen und zu konfigurieren.  Wenn Sie nicht [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] verwenden, können Sie die Clientanwendung für den Dienst mit [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) erstellen und konfigurieren.  
  
 In allen Themen in diesem Abschnitt wird davon ausgegangen, dass Sie Visual Studio 2011 als Entwicklungsumgebung verwenden.  Sollten Sie eine andere Entwicklungsumgebung verwenden, ignorieren Sie die [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]\-spezifischen Anweisungen.  
  
> [!NOTE]
>  Wenn Sie unter [!INCLUDE[wv](../../../includes/wv-md.md)] oder einer höheren Version des Windows\-Betriebssystems arbeiten, müssen Sie [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] starten. Klicken Sie hierzu im Startmenü mit der rechten Maustaste auf "Microsoft Visual Studio 2011", und klicken Sie anschließend auf **Als Administrator ausführen**.  Soll Visual Studio 2011 immer im Administratormodus ausgeführt werden, erstellen Sie eine Verknüpfung. Klicken Sie mit der rechten Maustaste auf die erstellte Verknüpfung, wählen Sie "Eigenschaften", klicken Sie auf die Registerkarte **Kompatibilität**, und aktivieren Sie das Kontrollkästchen **Programm als ein Administrator ausführen**.  Wenn Sie Visual Studio&\#160;2011 über diese Verknüpfung starten, wird es immer im Administratormodus ausgeführt.  
  
 Informationen zu Beispielanwendungen, die Sie auf Ihre Festplatte herunterladen und ausführen können, finden Sie in den Themen unter [Windows Communication Foundation Samples](http://msdn.microsoft.com/de-de/8ec9d192-5d81-4f64-bfd3-90c5e5858c91).  Informationen speziell zu diesem Thema finden Sie unter [Erste Schritte](../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
 Ausführlichere Informationen über das Erstellen von Diensten und Clients finden Sie unter [Basis\-WCF\-Programmierung](../../../docs/framework/wcf/basic-wcf-programming.md).  
  
## In diesem Abschnitt  
 [Gewusst wie: Definieren eines Dienstvertrags](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)  
 Beschreibt die Erstellung eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Vertrags mithilfe einer benutzerdefinierten Schnittstelle.  Der Vertrag definiert die Funktionalität, die vom Dienst verfügbar gemacht wird.  
  
 [Gewusst wie: Implementieren eines WCF\-Dienstvertrags](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 Beschreibt das Implementieren eines Dienstvertrags.  Sobald ein Vertrag definiert ist, müssen Sie ihn mit einer Dienstklasse implementieren.  
  
 [Gewusst wie: Hosten und Ausführen eines grundlegenden Diensts](../../../docs/framework/wcf/how-to-host-and-run-a-basic-wcf-service.md)  
 Beschreibt, wie im Code ein Endpunkt für den Dienst konfiguriert wird und wie der Dienst innerhalb einer Konsolenanwendung gehostet wird.  Zur Aktivierung muss der Dienst in einer Laufzeitumgebung konfiguriert und gehostet werden.  Diese Umgebung erstellt den Dienst, und steuert seinen Kontext sowie seine Lebensdauer.  
  
 [Vorgehensweise: Erstellen eines Clients](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 Beschreibt, wie Sie Metadaten abrufen, die zur Erstellung eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clientproxys aus einem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst verwendet werden.  Dieser Prozess verwendet die Funktion "Dienstverweis hinzufügen" in Visual Studio 2011.  
  
 [Gewusst wie: Konfigurieren eines Clients](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)  
 Beschreibt, wie ein WCF\-Client konfiguriert wird. Für die Konfiguration des Clients muss der Endpunkt angegeben werden, den der Client verwendet, um auf den Dienst zuzugreifen.  
  
 [Gewusst wie: Verwenden eines Clients](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)  
 Beschreibt, wie der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clientproxy verwendet wird, um Dienstvorgänge aufzurufen.  
  
## Referenz  
 <xref:System.ServiceModel.ServiceContractAttribute>  
  
 <xref:System.ServiceModel.OperationContractAttribute>  
  
## Verwandte Abschnitte  
 [Windows Communication Foundation Samples](http://msdn.microsoft.com/de-de/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)  
  
 [Grundlegender Programmierlebenszyklus](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
## Siehe auch  
 [Konzeptionelle Übersicht](../../../docs/framework/wcf/conceptual-overview.md)   
 [Anleitung zur Dokumentation](../../../docs/framework/wcf/guide-to-the-documentation.md)   
 [Was ist die Windows Communication Foundation?](../../../docs/framework/wcf/whats-wcf.md)   
 [Details zur WCF\-Funktion](../../../docs/framework/wcf/feature-details/index.md)