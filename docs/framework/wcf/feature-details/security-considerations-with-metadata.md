---
title: Sicherheitsüberlegungen für Metadaten
ms.date: 03/30/2017
ms.assetid: e78ef8ab-4f63-4656-ab93-b1deab2666d5
ms.openlocfilehash: c7a00d5abc9cc88b60208bd76fa8874f1fe00af9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275995"
---
# <a name="security-considerations-with-metadata"></a>Sicherheitsüberlegungen für Metadaten

Wenn Sie die Metadatenfeatures in Windows Communication Foundation (WCF) verwenden, sollten Sie die Sicherheits Implikationen beim Veröffentlichen, abrufen und Verwenden von Dienst Metadaten in Erwägung gezogen.  
  
## <a name="when-to-publish-metadata"></a>Veröffentlichen von Metadaten  

 WCF-Dienste veröffentlichen standardmäßig keine Metadaten. Zum Veröffentlichen von Metadaten für einen WCF-Dienst müssen Sie die Metadatenveröffentlichung explizit aktivieren, indem Sie Ihrem Dienst Metadatenendpunkte hinzufügen (siehe [Veröffentlichen von Metadaten](publishing-metadata.md)). Wird das Veröffentlichen von Metadaten nicht aktiviert, bietet der Dienst eine geringere Angriffsfläche, und auch das Risiko der ungewollten Preisgabe von Informationen ist geringer. Metadaten müssen nicht von allen Diensten veröffentlicht werden. Wenn keine Metadaten veröffentlicht werden müssen, können Sie die Funktion auch deaktiviert lassen. Beachten Sie, dass Sie weiterhin Metadaten und Client Code direkt aus ihren dienstassemblys generieren können, indem Sie das [Service Model Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)verwenden. Weitere Informationen zum Exportieren von Metadaten mithilfe von Svcutil.exe finden Sie unter Vorgehens [Weise: Verwenden von Svcutil.exe zum Exportieren von Metadaten aus kompiliertem Dienst Code](how-to-use-svcutil-exe-to-export-metadata-from-compiled-service-code.md).  
  
## <a name="publishing-metadata-using-a-secure-binding"></a>Veröffentlichen von Metadaten unter Verwendung einer sicheren Bindung  

 Die von WCF bereitgestellten standardmetadatenbindungen sind nicht sicher und ermöglichen den anonymen Zugriff auf die Metadaten. Die Dienst Metadaten, die von einem WCF-Dienst veröffentlicht werden, enthalten eine ausführliche Beschreibung des Dienstanbieter und können absichtlich oder unabsichtlich vertrauliche Informationen enthalten. So können in den Dienstmetadaten beispielsweise Informationen zu Infrastrukturvorgängen enthalten sein, die nicht für eine Veröffentlichung bestimmt sind. Mithilfe einer sicheren Bindung für den Metadatenendpunkt können die Dienstmetadaten vor nicht autorisiertem Zugriff geschützt werden. Metadatenendpunkte reagieren auf HTTP/GET-Anforderungen, von denen Secure Sockets Layer (SSL) zum Sichern der Metadaten verwendet werden kann. Weitere Informationen finden Sie unter Gewusst [wie: Sichern von Metadatenendpunkten](how-to-secure-metadata-endpoints.md).  
  
 Das Sichern der Metadatenendpunkte hat zudem den Vorteil, dass Dienstmetadaten auf sichere Weise und ohne Manipulations- oder Spoofinggefahr abgerufen werden können.  
  
## <a name="using-only-trusted-metadata"></a>Ausschließliches Verwenden vertrauenswürdiger Metadaten  

 Mithilfe von Dienstmetadaten lassen sich automatisch die zum Aufrufen des Diensts erforderlichen Laufzeitkomponenten konstruieren. Die Metadaten können auch zur Entwurfszeit verwendet werden, um eine Clientanwendung zu entwickeln, oder zur Laufzeit, um die vom Client zum Aufrufen des Diensts verwendete Bindung dynamisch zu aktualisieren.  
  
 Werden die Dienstmetadaten auf unsichere Weise abgerufen, können die Daten manipuliert oder gespooft werden. Manipulierte Metadaten können eine Umleitung des Clients zu Malware, fehlerhafte Sicherheitseinstellungen oder bösartige XML-Strukturen beinhalten. Metadatendokumente können groß sein und werden häufig im Dateisystem gespeichert. Verwenden Sie zum Schutz vor Manipulation und Spoofing beim Anfordern von Dienstmetadaten eine sichere Bindung (sofern vorhanden).  
  
## <a name="using-safe-techniques-for-processing-metadata"></a>Verwenden sicherer Techniken zum Verarbeiten von Metadaten  

 Dienstmetadaten werden häufig von einem Dienst über ein Netzwerk abgerufen. Hierzu werden standardisierte Protokolle wie WS-MetadataExchange (MEX) verwendet. Viele Metadatenformate enthalten Verweismechanismen, um auf weitere Metadaten zu verweisen. Verweise in WSDL (Web Services Description Language)-, XML-Schema- und MEX-Dokumenten werden vom <xref:System.ServiceModel.Description.MetadataExchangeClient>-Typ automatisch verarbeitet. Die Größe des aus den abgerufenen Metadaten erstellten <xref:System.ServiceModel.Description.MetadataSet>-Objekts verhält sich direkt proportional zum <xref:System.ServiceModel.Description.MetadataExchangeClient.MaximumResolvedReferences%2A>-Wert für die verwendete <xref:System.ServiceModel.Description.MetadataExchangeClient>-Instanz sowie zum `MaxReceivedMessageSize`-Wert für die von dieser <xref:System.ServiceModel.Description.MetadataExchangeClient>-Instanz verwendeten Bindung. Legen Sie geeignete Werte für diese Kontingente fest.  
  
 In WCF werden Dienst Metadaten als XML verarbeitet. Beim Verarbeiten von XML-Dokumenten schützen sich die Anwendungen selbst vor bösartigen XML-Strukturen. Verwenden Sie bei der <xref:System.Xml.XmlDictionaryReader> XML-Verarbeitung den mit entsprechenden Kontingenten, und legen Sie die- <xref:System.Xml.XmlTextReader.DtdProcessing%2A> Eigenschaft auf fest <xref:System.Xml.DtdProcessing.Prohibit>  
  
 Das Metadatensystem in WCF ist erweiterbar, und Metadatenerweiterungen können in der Anwendungs Konfigurationsdatei registriert werden (siehe [Erweitern des Metadatensystems](../extending/extending-the-metadata-system.md)). Von Metadatenerweiterungen kann beliebiger Code ausgeführt werden, weshalb die Anwendungskonfigurationsdatei mithilfe geeigneter Zugriffssteuerungslisten (Access Control Lists, ACLs) geschützt werden muss und ausschließlich vertrauenswürdige Implementierungen von Metadatenerweiterungen registriert werden dürfen.  
  
## <a name="validating-generated-clients"></a>Überprüfen von generierten Clients  

 Überprüfen Sie beim Generieren von Clientcode aus Metadaten, die von einer nicht vertrauenswürdigen Quelle abgerufen wurden, den generierten Clientcode, und stellen Sie sicher, dass der generierte Client mit den Sicherheitsrichtlinien der Clientanwendungen konform ist. Die Validierung der Einstellungen für die Clientbindung kann entweder mit einem Validierungsverhalten oder durch eine Sichtprüfung des generierten Codes erfolgen. Ein Beispiel für die Implementierung eines Clients, der Verhalten überprüft, finden Sie unter [Client Validierung](../samples/client-validation.md).  
  
## <a name="protecting-application-configuration-files"></a>Schützen von Anwendungskonfigurationsdateien  

 Mithilfe der Anwendungskonfigurationsdatei eines Diensts kann gesteuert werden, ob und auf welche Weise Metadaten veröffentlicht werden. Es empfiehlt sich, die Anwendungskonfigurationsdatei mit geeigneten Zugriffssteuerungslisten (Access Control Lists, ACLs) zu schützen, um so den Schutz vor Einstellungsänderungen durch einen möglichen Angreifer sicherzustellen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Sichern von Metadatenendpunkten](how-to-secure-metadata-endpoints.md)
- [Security](security.md)
