---
title: Sicherheitsüberlegungen für Metadaten
ms.date: 03/30/2017
ms.assetid: e78ef8ab-4f63-4656-ab93-b1deab2666d5
ms.openlocfilehash: 0dc060475f868923e8c7e4c87ef43ef5912c7ac5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61748368"
---
# <a name="security-considerations-with-metadata"></a>Sicherheitsüberlegungen für Metadaten
Wenn Sie die Metadaten-Features in Windows Communication Foundation (WCF) verwenden, sollten Sie die Sicherheitsaspekte bei der Veröffentlichung, abrufen und verwenden die Metadaten des Diensts.  
  
## <a name="when-to-publish-metadata"></a>Veröffentlichen von Metadaten  
 WCF-Dienste veröffentlichen Metadaten nicht standardmäßig. Zum Veröffentlichen von Metadaten für einen WCF-Dienst müssen Sie explizit Veröffentlichen von Metadaten durch das Hinzufügen von metadatenendpunkten zu Ihrem Dienst aktivieren (siehe [Veröffentlichungsmetadaten](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)). Wird das Veröffentlichen von Metadaten nicht aktiviert, bietet der Dienst eine geringere Angriffsfläche, und auch das Risiko der ungewollten Preisgabe von Informationen ist geringer. Metadaten müssen nicht von allen Diensten veröffentlicht werden. Wenn keine Metadaten veröffentlicht werden müssen, können Sie die Funktion auch deaktiviert lassen. Beachten Sie, dass Sie weiterhin Metadaten sowie Clientcode direkt über die Dienstassemblys mit generieren können die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Weitere Informationen zur Verwendung von Svcutil.exe zum Exportieren von Metadaten finden Sie unter [Vorgehensweise: Verwenden von Svcutil.exe zum Exportieren von Metadaten aus kompiliertem Dienstcode](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-export-metadata-from-compiled-service-code.md).  
  
## <a name="publishing-metadata-using-a-secure-binding"></a>Veröffentlichen von Metadaten unter Verwendung einer sicheren Bindung  
 Die Metadaten-standardbindungen, die WCF stellt nicht sicher sind, und sie können anonymen Zugriff auf die Metadaten auf. Die Metadaten des Diensts, die ein WCF-Dienst veröffentlicht enthält eine ausführliche Beschreibung des Diensts und kann absichtlich oder unabsichtlich vertrauliche Informationen enthalten. So können in den Dienstmetadaten beispielsweise Informationen zu Infrastrukturvorgängen enthalten sein, die nicht für eine Veröffentlichung bestimmt sind. Mithilfe einer sicheren Bindung für den Metadatenendpunkt können die Dienstmetadaten vor nicht autorisiertem Zugriff geschützt werden. Metadatenendpunkte reagieren auf HTTP/GET-Anforderungen, von denen Secure Sockets Layer (SSL) zum Sichern der Metadaten verwendet werden kann. Weitere Informationen finden Sie unter [Vorgehensweise: Sichere Metadatenendpunkte](../../../../docs/framework/wcf/feature-details/how-to-secure-metadata-endpoints.md).  
  
 Das Sichern der Metadatenendpunkte hat zudem den Vorteil, dass Dienstmetadaten auf sichere Weise und ohne Manipulations- oder Spoofinggefahr abgerufen werden können.  
  
## <a name="using-only-trusted-metadata"></a>Ausschließliches Verwenden vertrauenswürdiger Metadaten  
 Mithilfe von Dienstmetadaten lassen sich automatisch die zum Aufrufen des Diensts erforderlichen Laufzeitkomponenten konstruieren. Die Metadaten können auch zur Entwurfszeit verwendet werden, um eine Clientanwendung zu entwickeln, oder zur Laufzeit, um die vom Client zum Aufrufen des Diensts verwendete Bindung dynamisch zu aktualisieren.  
  
 Werden die Dienstmetadaten auf unsichere Weise abgerufen, können die Daten manipuliert oder gespooft werden. Manipulierte Metadaten können eine Umleitung des Clients zu Malware, fehlerhafte Sicherheitseinstellungen oder bösartige XML-Strukturen beinhalten. Metadatendokumente können groß sein und werden häufig im Dateisystem gespeichert. Verwenden Sie zum Schutz vor Manipulation und Spoofing beim Anfordern von Dienstmetadaten eine sichere Bindung (sofern vorhanden).  
  
## <a name="using-safe-techniques-for-processing-metadata"></a>Verwenden sicherer Techniken zum Verarbeiten von Metadaten  
 Dienstmetadaten werden häufig von einem Dienst über ein Netzwerk abgerufen. Hierzu werden standardisierte Protokolle wie WS-MetadataExchange (MEX) verwendet. Viele Metadatenformate enthalten Verweismechanismen, um auf weitere Metadaten zu verweisen. Verweise in WSDL (Web Services Description Language)-, XML-Schema- und MEX-Dokumenten werden vom <xref:System.ServiceModel.Description.MetadataExchangeClient>-Typ automatisch verarbeitet. Die Größe des aus den abgerufenen Metadaten erstellten <xref:System.ServiceModel.Description.MetadataSet>-Objekts verhält sich direkt proportional zum <xref:System.ServiceModel.Description.MetadataExchangeClient.MaximumResolvedReferences%2A>-Wert für die verwendete <xref:System.ServiceModel.Description.MetadataExchangeClient>-Instanz sowie zum `MaxReceivedMessageSize`-Wert für die von dieser <xref:System.ServiceModel.Description.MetadataExchangeClient>-Instanz verwendeten Bindung. Legen Sie geeignete Werte für diese Kontingente fest.  
  
 In WCF wird Dienstmetadaten als XML verarbeitet. Beim Verarbeiten von XML-Dokumenten schützen sich die Anwendungen selbst vor bösartigen XML-Strukturen. Verwenden der <xref:System.Xml.XmlDictionaryReader> mit geeigneten Kontingenten, beim Verarbeiten von XML, und legen Sie außerdem die <xref:System.Xml.XmlTextReader.DtdProcessing%2A> Eigenschaft <xref:System.Xml.DtdProcessing.Prohibit>.  
  
 Das Metadatensystem in WCF ist erweiterbar und Metadatenerweiterungen können in der Anwendungskonfigurationsdatei registriert werden (siehe [Erweitern des Metadatensystems](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)). Von Metadatenerweiterungen kann beliebiger Code ausgeführt werden, weshalb die Anwendungskonfigurationsdatei mithilfe geeigneter Zugriffssteuerungslisten (Access Control Lists, ACLs) geschützt werden muss und ausschließlich vertrauenswürdige Implementierungen von Metadatenerweiterungen registriert werden dürfen.  
  
## <a name="validating-generated-clients"></a>Überprüfen von generierten Clients  
 Überprüfen Sie beim Generieren von Clientcode aus Metadaten, die von einer nicht vertrauenswürdigen Quelle abgerufen wurden, den generierten Clientcode, und stellen Sie sicher, dass der generierte Client mit den Sicherheitsrichtlinien der Clientanwendungen konform ist. Die Validierung der Einstellungen für die Clientbindung kann entweder mit einem Validierungsverhalten oder durch eine Sichtprüfung des generierten Codes erfolgen. Ein Beispiel dafür, wie einen Client implementiert, die verhaltensprüfung finden Sie unter [Clientvalidierung](../../../../docs/framework/wcf/samples/client-validation.md).  
  
## <a name="protecting-application-configuration-files"></a>Schützen von Anwendungskonfigurationsdateien  
 Mithilfe der Anwendungskonfigurationsdatei eines Diensts kann gesteuert werden, ob und auf welche Weise Metadaten veröffentlicht werden. Es empfiehlt sich, die Anwendungskonfigurationsdatei mit geeigneten Zugriffssteuerungslisten (Access Control Lists, ACLs) zu schützen, um so den Schutz vor Einstellungsänderungen durch einen möglichen Angreifer sicherzustellen.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Sichere Metadatenendpunkte](../../../../docs/framework/wcf/feature-details/how-to-secure-metadata-endpoints.md)
- [Sicherheit](../../../../docs/framework/wcf/feature-details/security.md)
