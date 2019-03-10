---
title: Entwickeln von Vertrag zuerst-Workflowdiensten
ms.date: 03/30/2017
ms.assetid: e5dbaa7b-005f-4330-848d-58ac4f42f093
ms.openlocfilehash: c326f91bc8673180db755a91ab080bcf0ba72052
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721787"
---
# <a name="contract-first-workflow-service-development"></a>Entwickeln von Vertrag zuerst-Workflowdiensten
Beginnend mit [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], Windows Workflow Foundation (WF)-Funktionen zur verbesserten Integration zwischen Webdiensten und Workflows in Form der Vertrag zuerst-Workflowentwicklung. Das Tool für die Vertrag zuerst-Workflowentwicklung ermöglicht es Ihnen, den Vertrag zuerst im Code zu entwerfen. Das Tool generiert dann automatisch eine Aktivitätsvorlage für die Vertragsvorgänge in der Toolbox. Dieses Thema enthält eine Übersicht darüber, wie die Aktivitäten und Eigenschaften in einer Workflowdienstzuordnung den Attributen eines Dienstvertrags zugeordnet werden. Ein ausführliches Beispiel zum Erstellen eines Vertrag zuerst-Workflowdiensts, finden Sie unter [Vorgehensweise: Erstellen eines Workflowdiensts, das Verarbeiten eines vorhandenen Dienstvertrags](how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md).  
  
## <a name="in-this-topic"></a>In diesem Thema  
  
-   [Zuordnen von dienstvertragsattributen zu workflowattributen](contract-first-workflow-service-development.md#MappingAttributes)  
  
    -   [Dienstvertragsattribute](contract-first-workflow-service-development.md#ServiceContract)  
  
    -   [Vorgangsvertragsattribute](contract-first-workflow-service-development.md#OperationContract)  
  
    -   [Nachrichtenvertragsattribute](contract-first-workflow-service-development.md#MessageContract)  
  
    -   [Datenvertragsattribute](contract-first-workflow-service-development.md#DataContract)  
  
    -   [Fehlervertragsattribute](contract-first-workflow-service-development.md#FaultContract)  
  
-   [Zusätzliche Support- und Implementierungsinformationen](contract-first-workflow-service-development.md#AdditionalSupport)  
  
    -   [Nicht unterstützte dienstvertragsfunktionen](contract-first-workflow-service-development.md#UnsupportedFeatures)  
  
    -   [Generierung konfigurierter messagingaktivitäten](contract-first-workflow-service-development.md#ActivityGeneration)  
  
## <a name="MappingAttributes"></a> Zuordnen von dienstvertragsattributen zu workflowattributen  
 Die Tabellen in den folgenden Abschnitten enthalten die verschiedenen WCF-Attribute und -Eigenschaften und veranschaulichen die Zuordnung zu Messagingaktivitäten und Eigenschaften in einem Vertrag zuerst-Workflow.  
  
-   [Dienstvertragsattribute](contract-first-workflow-service-development.md#ServiceContract)  
  
-   [Vorgangsvertragsattribute](contract-first-workflow-service-development.md#OperationContract)  
  
-   [Nachrichtenvertragsattribute](contract-first-workflow-service-development.md#MessageContract)  
  
-   [Datenvertragsattribute](contract-first-workflow-service-development.md#DataContract)  
  
-   [Fehlervertragsattribute](contract-first-workflow-service-development.md#FaultContract)  
  
### <a name="ServiceContract"></a> Dienstvertragsattribute  
  
|Eigenschaftenname|Unterstützt|Beschreibung|WF-Validierung|  
|-------------------|---------------|-----------------|-------------------|  
|CallbackContract|Nein|Ruft den Typ des Rückrufvertrags ab oder legt ihn fest, wenn es sich beim Vertrag um einen Duplexvertrag handelt.|(Nicht zutreffend)|  
|ConfigurationName|Nein|Ruft den Namen ab, mit dem der Dienst in einer Anwendungskonfigurationsdatei gesucht wird, oder legt ihn fest.|(Nicht zutreffend)|  
|HasProtectionLevel|Ja|Ruft einen Wert ab, der angibt, ob dem Member eine Schutzebene zugewiesen wurde.|Receive.ProtectionLevel darf nicht NULL sein.|  
|Name|Ja|Ruft ab oder legt den Namen für die \<PortType >-Elements in Web Services Description Language (WSDL).|Receive.ServiceContractName.LocalName sollte übereinstimmen.|  
|Namespace|Ja|Ruft ab oder legt den Namespace der \<PortType >-Elements in Web Services Description Language (WSDL).|Receive.ServiceContractName.NameSpace sollte übereinstimmen.|  
|ProtectionLevel|Ja|Gibt an, ob die Vertragsbindung den Wert der ProtectionLevel-Eigenschaft unterstützen muss.|Receive.ProtectionLevel sollte übereinstimmen.|  
|SessionMode|Nein|Ruft ab, ob Sitzungen zugelassen, nicht zugelassen oder erforderlich sind, oder legt dies fest.|(Nicht zutreffend)|  
|TypeId|Nein|Ruft bei der Implementierung in einer abgeleiteten Klasse einen eindeutigen Bezeichner für dieses Attribut ab. (Vom Attribut geerbt).|(Nicht zutreffend)|  
  
 Unterabschnittstext hier einfügen.  
  
### <a name="OperationContract"></a> Vorgangsvertragsattribute  
  
|Eigenschaftenname|Unterstützt|Beschreibung|WF-Validierung|  
|-------------------|---------------|-----------------|-------------------|  
|Aktion|Ja|Ruft ab oder legt die WS-Adressierungsaktion der Anforderungsnachricht fest.|Receive.Action sollte übereinstimmen.|  
|AsyncPattern|Nein|Gibt an, dass ein Vorgang asynchron implementiert wird eine Begin\<MethodName > und End\<MethodName >-Methode bestehenden Methodenpaars, in einem Dienstvertrag.|(Nicht zutreffend)|  
|HasProtectionLevel|Ja|Ruft einen Wert ab, der angibt, ob die Nachrichten für diesen Vorgang verschlüsselt oder signiert werden müssen oder beides.|Receive.ProtectionLevel darf nicht NULL sein.|  
|IsInitiating|Nein|Ruft einen Wert ab, der angibt, ob die Methode einen Vorgang implementiert, der eine Sitzung auf dem Server initiieren kann (sofern eine solche Sitzung vorhanden ist), oder legt diesen fest.|(Nicht zutreffend)|  
|IsOneWay|Ja|Ruft einen Wert ab, der angibt, ob ein Vorgang eine Antwortnachricht zurückgibt, oder legt diesen fest.|(Kein SendReply für dieses Empfangsvorgang ODER kein ReceiveReply für diesen Sendevorgang).|  
|IsTerminating|Nein|Ruft einen Wert ab, der angibt, ob der Dienstvorgang bewirkt, dass der Server die Sitzung schließt, nachdem die Antwortnachricht gesendet wurde.|(Nicht zutreffend)|  
|Name|Ja|Ruft den Namen des Vorgangs ab oder legt diesen fest.|Receive.OperationName sollte übereinstimmen.|  
|ProtectionLevel|Ja|Ruft einen Wert ab, der angibt, ob die Nachrichten eines Vorgangs verschlüsselt oder signiert werden müssen oder beides beziehungsweise legt ihn fest.|Receive.ProtectionLevel sollte übereinstimmen.|  
|ReplyAction|Ja|Ruft ab oder legt den Wert der SOAP-Aktion für die Antwortnachricht des Vorgangs fest.|SendReply.Action sollte übereinstimmen.|  
|TypeId|Nein|Ruft bei der Implementierung in einer abgeleiteten Klasse einen eindeutigen Bezeichner für dieses Attribut ab. (Vom Attribut geerbt).|(Nicht zutreffend)|  
  
### <a name="MessageContract"></a> Nachrichtenvertragsattribute  
  
|Eigenschaftenname|Unterstützt|Beschreibung|WF-Validierung|  
|-------------------|---------------|-----------------|-------------------|  
|HasProtectionLevel|Ja|Ruft einen Wert ab, der angibt, ob die Nachricht über eine Schutzebene verfügt.|Keine Validierung (Receive.Content und SendReply.Content müssen mit dem Nachrichtenvertragstyp übereinstimmen).|  
|IsWrapped|Ja|Ruft einen Wert ab oder legt einen Wert fest, der angibt, ob der Nachrichtentext über ein Wrapperelement verfügt.|Keine Validierung (Receive.Content und Sendreply.Content müssen mit dem Nachrichtenvertragstyp übereinstimmen).|  
|ProtectionLevel|Nein|Ruft einen Wert ab, der angibt, ob die Nachricht verschlüsselt oder signiert werden muss oder beides, oder legt diesen Wert fest.|(Nicht zutreffend)|  
|TypeId|Ja|Ruft bei der Implementierung in einer abgeleiteten Klasse einen eindeutigen Bezeichner für dieses Attribut ab. (Vom Attribut geerbt).|Keine Validierung (Receive.Content und SendReply.Content müssen mit dem Nachrichtenvertragstyp übereinstimmen).|  
|WrapperName|Ja|Ruft den Wrapperelementnamen des Nachrichtentexts ab, oder legt ihn fest.|Keine Validierung (Receive.Content und SendReply.Content müssen mit dem Nachrichtenvertragstyp übereinstimmen).|  
|WrapperNamespace|Nein|Ruft den Namespace des Nachrichtentext-Wrapperelements ab oder legt ihn fest.|(Nicht zutreffend)|  
  
### <a name="DataContract"></a> Datenvertragsattribute  
  
|Eigenschaftenname|Unterstützt|Beschreibung|WF-Validierung|  
|-------------------|---------------|-----------------|-------------------|  
|IsReference|Nein|Ruft einen Wert ab oder legt einen Wert fest, der angibt, ob Objektverweisdaten beizubehalten sind.|(Nicht zutreffend)|  
|Name|Ja|Ruft den Namen des Datenvertrags für den Typ ab oder legt ihn fest.|Keine Validierung (Receive.Content und SendReply.Content müssen mit dem Nachrichtenvertragstyp übereinstimmen).|  
|Namespace|Ja|Ruft den Namespace des Datenvertrags für den Typ ab oder legt ihn fest.|Keine Validierung (Receive.Content und SendReply.Content müssen mit dem Nachrichtenvertragstyp übereinstimmen).|  
|TypeId|Nein|Ruft bei der Implementierung in einer abgeleiteten Klasse einen eindeutigen Bezeichner für dieses Attribut ab. (Vom Attribut geerbt).|(Nicht zutreffend)|  
  
### <a name="FaultContract"></a> Fehlervertragsattribute  
  
|Eigenschaftenname|Unterstützt|Beschreibung|WF-Validierung|  
|-------------------|---------------|-----------------|-------------------|  
|Aktion|Ja|Ruft die Aktion der SOAP-Fehlernachricht ab, die als Bestandteil des Vorgangsvertrags angegeben wurde, oder legt sie fest.|SendReply.Action sollte übereinstimmen.|  
|DetailType|Ja|Ruft den Typ eines serialisierbaren Objekts ab, das Fehlerinformationen enthält.|SendReply.Content sollte dem Typ entsprechen.|  
|HasProtectionLevel|Nein|Ruft einen Wert ab, der angibt, ob der SOAP-Fehlernachricht eine Sicherheitsebene zugewiesen wurde.|(Nicht zutreffend)|  
|Name|Nein|Ruft ab oder legt den Namen der Fehlernachricht in WSDL (Web Services Description Language) fest.|(Nicht zutreffend)|  
|Namespace|Nein|Ruft den Namespace des SOAP-Fehlers ab oder legt diesen fest.|(Nicht zutreffend)|  
|ProtectionLevel|Nein|Gibt die Sicherheitsebene an, die der SOAP-Fehler von der Bindung fordert.|(Nicht zutreffend)|  
|TypeId|Nein|Ruft bei der Implementierung in einer abgeleiteten Klasse einen eindeutigen Bezeichner für dieses Attribut ab. (Vom Attribut geerbt).|(Nicht zutreffend)|  
  
## <a name="AdditionalSupport"></a> Zusätzliche Support- und Implementierungsinformationen  
  
-   [Nicht unterstützte dienstvertragsfunktionen](contract-first-workflow-service-development.md#UnsupportedFeatures)  
  
-   [Generierung konfigurierter messagingaktivitäten](contract-first-workflow-service-development.md#ActivityGeneration)  
  
### <a name="UnsupportedFeatures"></a> Nicht unterstützte dienstvertragsfunktionen  
  
-   Die Verwendung von TPL (Task Parallel Library)-Tasks in den Verträgen wird nicht unterstützt.  
  
-   Die Vererbung in Dienstverträgen wird nicht unterstützt.  
  
### <a name="ActivityGeneration"></a> Generierung konfigurierter messagingaktivitäten  
 Zwei öffentliche statische Methoden werden der <xref:System.ServiceModel.Activities.Receive>-Aktivität und der <xref:System.ServiceModel.Activities.SendReply>-Aktivität hinzugefügt, um bei Verwendung von Vertrag zuerst-Workflowdiensten die Generierung von vorkonfigurierten Nachrichtenaktivitäten zu unterstützen.  
  
-   <xref:System.ServiceModel.Activities.Receive.FromOperationDescription%2A?displayProperty=nameWithType>  
  
-   <xref:System.ServiceModel.Activities.SendReply.FromOperationDescription%2A?displayProperty=nameWithType>  
  
 Die Aktivität, die durch diese Methoden generiert wird, sollte die Vertragsüberprüfung erfolgreich abschließen. Daher werden diese Methoden intern als Teil der Validierungslogik für <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply> verwendet. 
  <xref:System.ServiceModel.Activities.Receive.OperationName%2A>, <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>, <xref:System.ServiceModel.Activities.Receive.Action%2A>, <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>, <xref:System.ServiceModel.Activities.Receive.ProtectionLevel%2A> und <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> werden alle vorkonfiguriert, um dem importierten Vertrag zu entsprechen. Auf der Seite "Content-Eigenschaften" für die Aktivitäten im Workflow-Designer die **Nachricht** oder **Parameter** Abschnitte sind auch so vorkonfiguriert, dass dem Vertrag entsprechen.  
  
 WCF-fehlerverträge auch behandelt werden, indem Sie einen separaten Satz von zurückgeben konfiguriert <xref:System.ServiceModel.Activities.SendReply> Aktivitäten für jeden Fehler, die in angezeigt wird, werden die <xref:System.ServiceModel.Description.OperationDescription.Faults%2A> <xref:System.ServiceModel.Description.FaultDescriptionCollection>.  
  
 In anderen Teilen der <xref:System.ServiceModel.Description.OperationDescription> , die von WF-Diensten derzeit (z. B. WebGet-/WebInvoke-Verhaltensweisen oder Verhaltensweisen benutzerdefinierter Vorgänge) nicht unterstützt werden, die API ignoriert diese Werte als Teil der Generierung und Konfiguration. Es werden keine Ausnahmen ausgelöst.
