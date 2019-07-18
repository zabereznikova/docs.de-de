---
title: WCF-Konfigurationsschema
ms.date: 03/30/2017
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
ms.openlocfilehash: baea1e49bce10054530afa5b6f282023d5ceb981
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755818"
---
# <a name="wcf-configuration-schema"></a>WCF-Konfigurationsschema
Windows Communication Foundation (WCF)-Konfigurationselemente können Sie WCF-Dienst und Client-Anwendungen zu konfigurieren. Sie können das [Configuration Editor-Tool (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) verwenden, um Konfigurationsdateien für Clients und Dienste zu erstellen und zu bearbeiten. Da die Konfigurationsdateien als XML formatiert sind, müssen Sie mit XML vertraut sein, wenn Sie diese manuell in einem Texteditor bearbeiten möchten. Andernfalls treten möglicherweise Probleme auf, wie ein nicht gefundenes XML-Elementtag oder -attribut. Das liegt daran, dass bei XML-Elementtags und -attributen zwischen Groß- und Kleinschreibung unterschieden wird.  
  
 Das WCF-Konfigurationssystem basiert auf der <xref:System.Configuration> Namespace. Deshalb können Sie alle Standardfunktionen verwenden, die vom <xref:System.Configuration>-Namespace bereitgestellt werden, wie die Konfigurationssperre, die Verschlüsselung und das Zusammenführen, um die Sicherheit Ihrer Anwendung und ihrer Konfiguration zu erhöhen. Weitere Informationen über diese Konzepte finden Sie in den folgenden Themen.  
  
 [Encrypting Configuration Information (Verschlüsseln von Konfigurationsinformationen)](https://go.microsoft.com/fwlink/?LinkId=95337)  
  
 [Locking Configuration Settings (Sperren von Konfigurationseinstellungen)](https://go.microsoft.com/fwlink/?LinkId=95338)  
  
 In diesem Abschnitt werden alle möglichen Werte eines Konfigurationselements sowie seine Interaktion mit anderen WCF-Konfigurationselementen beschrieben. Die folgende Zuordnung illustriert das WCF-Konfigurationsschema:  
  
 ![Diagramm die WCF-Konfigurationsschema zeigt.](./media/index/windows-communication-foundation-configuration-schema.gif)  
  
> [!CAUTION]
>  Sie sollten den WCF-Konfigurationsabschnitten in Ihren Anwendungskonfigurationsdateien ("App.config") mit entsprechenden Access Control Lists (ACL) auf mögliche Sicherheitsrisiken zu verhindern, dass schützen.  So sollten Sie z.&amp;#160;B. sicherstellen, dass nur die entsprechenden Personen auf die Sicherheitseinstellungen von Anwendungsbindungen oder auf den Dienstmodellabschnitt der Konfigurationsdatei eines Diensts zugreifen oder diese ändern können.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
 Beschreibt das `ServiceModel`-Element.  
  
 [\<system.serviceModel.activation>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)  
 Konfiguriert das SMSvcHost.exe-Tool.  
  
 [\<system.runtime.serialization>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
 Das Element der obersten Ebene zum Festlegen von Optionen für die Verwendung von Serialisierern, wie z. B. <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Konfigurieren von Windows Communication Foundation-Anwendungen](../../../wcf/configuring-services.md)  
 Beschreibt, wie WCF-Dienste und Clients zu konfigurieren.
