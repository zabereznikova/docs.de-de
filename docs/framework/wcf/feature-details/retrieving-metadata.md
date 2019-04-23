---
title: Abrufen von Metadaten
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WCF], retrieving
ms.assetid: 18d8ba4c-af0f-4827-a50b-4202d767bacc
ms.openlocfilehash: bb415d88c2bae75cb16aa137bdf867eb463afa63
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152398"
---
# <a name="retrieving-metadata"></a>Abrufen von Metadaten
Das Abrufen von Metadaten ist der Prozess, Metadaten von einem Metadatenendpunkt, wie einem MEX-Medadatenendpunkt (WS-MetadataExchange) oder einem HTTP/GET-Metadatenendpunkt, anzufordern und abzurufen.  
  
## <a name="retrieving-metadata-from-the-command-line-using-svcutilexe"></a>Abrufen von Metadaten mit Svcutil.exe in der Befehlszeile  
 Sie können Dienstmetadaten mit WS-MetadataExchange- oder HTTP/GET-Anforderungen mithilfe von Abrufen der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Tool und das Übergeben der `/target:metadata` Switches und einer Adresse. Svcutil.exe lädt die Metadaten bei der angegebenen Adresse herunter und speichert die Datei auf Datenträger. Svcutil.exe verwendet intern eine <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType>-Instanz und lädt die <xref:System.ServiceModel.Description.IMetadataExchange>-Endpunktkonfiguration, deren Name mit dem Schema der an Svcutil.exe als Eingabe weitergegebenen Adresse übereinstimmt, aus der Konfiguration.  
  
## <a name="retrieving-metadata-programmatically-using-the-metadataexchangeclient"></a>Programmgesteuertes Abrufen von Metadaten mit dem MetadataExchangeClient  
 Windows Communication Foundation (WCF) kann Dienstmetadaten mithilfe standardisierter Protokolle, z. B. WS-MetadataExchange- und HTTP/GET-Anforderungen abgerufen werden. Beide Protokolle werden vom <xref:System.ServiceModel.Description.MetadataExchangeClient>-Typ unterstützt. Dienstmetadaten werden mit dem <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType>-Typ abgerufen, indem eine Adresse für den Metadatenendpunkt und eine optionale Bindung angegeben werden. Bei der von einer <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType>-Instanz verwendeten Bindung kann es sich um eine der Standardbindungen aus der statischen <xref:System.ServiceModel.Description.MetadataExchangeBindings>-Klasse, eine vom Benutzer angegebene Bindung oder eine aus einer Endpunktkonfiguration für den `IMetadataExchange`-Vertrag geladene Bindung handeln. Der <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> kann auch HTTP-URL-Verweise auf Metadaten mit dem <xref:System.Net.HttpWebRequest>-Typ auflösen.  
  
 Standardmäßig wird eine <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType>-Instanz an eine einzelne <xref:System.ServiceModel.ChannelFactory>-Instanz gebunden. Sie können die <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>-Instanz, die von einem <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> verwendet wird, durch Überschreiben der virtuellen <xref:System.ServiceModel.Description.MetadataExchangeClient.GetChannelFactory%2A>-Methode ändern oder ersetzen. Ebenso können Sie die <xref:System.Net.HttpWebRequest>-Instanz, die von einem <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> zur Erstellung von HTTP/GET-Anforderungen verwendet wird, durch Überschreiben der virtuellen <xref:System.ServiceModel.Description.MetadataExchangeClient.GetWebRequest%2A?displayProperty=nameWithType>-Methode ändern oder ersetzen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Verwenden von Svcutil.exe zum Herunterladen von Metadatendokumenten](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)  
 Veranschaulicht, wie Svcutil.exe zum Herunterladen von Metadatendokumenten verwendet wird.  
  
 [Vorgehensweise: Verwenden von MetadataResolver, um Bindungsmetadaten dynamisch zu erhalten](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md)  
 Veranschaulicht, wie der <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType> verwendet wird, um Bindungsmetadaten zur Laufzeit dynamisch zu erhalten.  
  
 [Vorgehensweise: Verwenden von MetadataExchangeClient zum Abrufen von Metadaten](../../../../docs/framework/wcf/feature-details/how-to-use-metadataexchangeclient-to-retrieve-metadata.md)  
 Veranschaulicht, wie eine <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType>-Klasse zum Herunterladen von Metadatendateien in ein <xref:System.ServiceModel.Description.MetadataSet?displayProperty=nameWithType>-Objekt verwendet wird, das <xref:System.ServiceModel.Description.MetadataSection?displayProperty=nameWithType>-Objekte zum Schreiben in Dateien oder für andere Zwecke enthält.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Description.MetadataExchangeClient>
