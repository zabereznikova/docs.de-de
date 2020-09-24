---
title: WCF-Konfigurationsschema
ms.date: 03/30/2017
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
ms.openlocfilehash: ab64b41e6e79c934ac0145dd7eec0a943f5dc473
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165129"
---
# <a name="wcf-configuration-schema"></a>WCF-Konfigurationsschema

Windows Communication Foundation (WCF)-Konfigurationselemente ermöglichen es Ihnen, WCF-Dienst-und-Client Anwendungen zu konfigurieren. Sie können das [Configuration Editor-Tool (SvcConfigEditor.exe)](../../../wcf/configuration-editor-tool-svcconfigeditor-exe.md) verwenden, um Konfigurationsdateien für Clients und Dienste zu erstellen und zu bearbeiten. Da die Konfigurationsdateien als XML formatiert sind, müssen Sie mit XML vertraut sein, wenn Sie diese manuell in einem Texteditor bearbeiten möchten. Andernfalls treten möglicherweise Probleme auf, wie ein nicht gefundenes XML-Elementtag oder -attribut. Das liegt daran, dass bei XML-Elementtags und -attributen zwischen Groß- und Kleinschreibung unterschieden wird.  
  
 Das WCF-Konfigurationssystem basiert auf dem- <xref:System.Configuration> Namespace. Deshalb können Sie alle Standardfunktionen verwenden, die vom <xref:System.Configuration>-Namespace bereitgestellt werden, wie die Konfigurationssperre, die Verschlüsselung und das Zusammenführen, um die Sicherheit Ihrer Anwendung und ihrer Konfiguration zu erhöhen. Weitere Informationen über diese Konzepte finden Sie in den folgenden Themen.  
  
 [Encrypting Configuration Information (Verschlüsseln von Konfigurationsinformationen)](/previous-versions/aspnet/53tyfkaw(v=vs.100))  
  
 [Locking Configuration Settings (Sperren von Konfigurationseinstellungen)](/previous-versions/aspnet/55th21y4(v=vs.100))  
  
 In diesem Abschnitt werden alle möglichen Werte eines Konfigurationselements sowie seine Interaktion mit anderen WCF-Konfigurationselementen beschrieben. Das WCF-Konfigurations Schema wird in der folgenden Abbildung veranschaulicht:  
  
 ![Diagramm, in dem das WCF-Konfigurations Schema angezeigt wird.](./media/index/windows-communication-foundation-configuration-schema.gif)  
  
> [!CAUTION]
> Sie sollten WCF-Konfigurations Abschnitte in ihren Anwendungs Konfigurationsdateien (app.config) mit entsprechenden Access Control Listen (ACL) schützen, um potenzielle Sicherheitsbedrohungen zu verhindern.  So sollten Sie z.&#160;B. sicherstellen, dass nur die entsprechenden Personen auf die Sicherheitseinstellungen von Anwendungsbindungen oder auf den Dienstmodellabschnitt der Konfigurationsdatei eines Diensts zugreifen oder diese ändern können.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [\<system.serviceModel>](system-servicemodel.md)  
 Beschreibt das `ServiceModel`-Element.  
  
 [\<system.serviceModel.activation>](system-servicemodel-activation.md)  
 Konfiguriert das SMSvcHost.exe-Tool.  
  
 [\<system.runtime.serialization>](system-runtime-serialization.md)  
 Das Element der obersten Ebene zum Festlegen von Optionen für die Verwendung von Serialisierern, wie z. B. <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [Configuring Windows Communication Foundation Applications](../../../wcf/configuring-services.md)  
 Beschreibt das Konfigurieren von WCF-Diensten und-Clients.
