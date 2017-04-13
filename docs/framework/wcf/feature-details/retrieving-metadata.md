---
title: "Abrufen von Metadaten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Metadaten [WCF], Abrufen"
ms.assetid: 18d8ba4c-af0f-4827-a50b-4202d767bacc
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Abrufen von Metadaten
Das Abrufen von Metadaten ist der Prozess, Metadaten von einem Metadatenendpunkt, wie einem MEX\-Medadatenendpunkt \(WS\-MetadataExchange\) oder einem HTTP\/GET\-Metadatenendpunkt, anzufordern und abzurufen.  
  
## Abrufen von Metadaten mit Svcutil.exe in der Befehlszeile  
 Sie können Dienstmetadaten mit WS\-MetadataExchange\- oder HTTP\/GET\-Anforderungen unter Verwendung des [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)\-Tools und durch Weitergabe des `/target:metadata`\-Switches und einer Adresse abrufen.Svcutil.exe lädt die Metadaten bei der angegebenen Adresse herunter und speichert die Datei auf Datenträger.Svcutil.exe verwendet intern eine <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName>\-Instanz und lädt die <xref:System.ServiceModel.Description.IMetadataExchange>\-Endpunktkonfiguration, deren Name mit dem Schema der an Svcutil.exe als Eingabe weitergegebenen Adresse übereinstimmt, aus der Konfiguration.  
  
## Programmgesteuertes Abrufen von Metadaten mit dem MetadataExchangeClient  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] kann Dienstmetadaten mithilfe standardisierter Protokolle, wie z. B. WS\-MetadataExchange\- und HTTP\/GET\-Anforderungen, abrufen.Beide Protokolle werden vom <xref:System.ServiceModel.Description.MetadataExchangeClient>\-Typ unterstützt.Dienstmetadaten werden mit dem <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName>\-Typ abgerufen, indem eine Adresse für den Metadatenendpunkt und eine optionale Bindung angegeben werden.Die von einer <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName>\-Instanz verwendete Bindung kann eine der Standardbindungen aus der statischen <xref:System.ServiceModel.Description.MetadataExchangeBindings>\-Klasse, eine vom Benutzer angegebene Bindung oder eine aus einer Endpunktkonfiguration für den `IMetadataExchange`\-Vertrag geladene Bindung sein.Der <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> kann auch HTTP\-URL\-Verweise auf Metadaten mit dem <xref:System.Net.HttpWebRequest>\-Typ auflösen.  
  
 Standardmäßig wird eine <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName>\-Instanz an eine einzelne <xref:System.ServiceModel.ChannelFactory>\-Instanz gebunden.Sie können die <xref:System.ServiceModel.ChannelFactory?displayProperty=fullName>\-Instanz, die von einem <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> verwendet wird, durch Überschreiben der virtuellen <xref:System.ServiceModel.Description.MetadataExchangeClient.GetChannelFactory%2A>\-Methode ändern oder ersetzen.Ebenso können Sie die <xref:System.Net.HttpWebRequest>\-Instanz, die von einem <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> zur Erstellung von HTTP\/GET\-Anforderungen verwendet wird, durch Überschreiben der virtuellen <xref:System.ServiceModel.Description.MetadataExchangeClient.GetWebRequest%2A?displayProperty=fullName>\-Methode ändern oder ersetzen.  
  
## In diesem Abschnitt  
 [Gewusst wie: Verwenden von Svcutil.exe zum Herunterladen von Metadatendokumenten](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)  
 Veranschaulicht, wie Svcutil.exe zum Herunterladen von Metadatendokumenten verwendet wird.  
  
 [Vorgehensweise: Verwenden von MetadataResolver, um Bindungsmetadaten dynamisch zu erhalten](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md)  
 Veranschaulicht, wie der <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=fullName> verwendet wird, um Bindungsmetadaten zur Laufzeit dynamisch zu erhalten.  
  
 [Vorgehensweise: Die Verwendung von MetadataExchangeClient zum Abrufen von Metadaten](../../../../docs/framework/wcf/feature-details/how-to-use-metadataexchangeclient-to-retrieve-metadata.md)  
 Veranschaulicht, wie eine <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName>\-Klasse zum Herunterladen von Metadatendateien in ein <xref:System.ServiceModel.Description.MetadataSet?displayProperty=fullName>\-Objekt verwendet wird, das <xref:System.ServiceModel.Description.MetadataSection?displayProperty=fullName>\-Objekte zum Schreiben in Dateien oder für andere Zwecke enthält.  
  
## Siehe auch  
 <xref:System.ServiceModel.Description.MetadataExchangeClient>