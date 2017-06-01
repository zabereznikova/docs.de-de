---
title: "Entwickeln von Vertrag zuerst-Workflowdiensten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e5dbaa7b-005f-4330-848d-58ac4f42f093
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Entwickeln von Vertrag zuerst-Workflowdiensten
Ab [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] verbessern [!INCLUDE[wf](../../../includes/wf-md.md)] \-Funktionen die Integration zwischen Webdiensten und Workflows in Form der Vertrag zuerst\-Workflowentwicklung.Das Tool für die Vertrag zuerst\-Workflowentwicklung ermöglicht es Ihnen, den Vertrag zuerst im Code zu entwerfen.Das Tool generiert dann automatisch eine Aktivitätsvorlage für die Vertragsvorgänge in der Toolbox.Dieses Thema enthält eine Übersicht darüber, wie die Aktivitäten und Eigenschaften in einer Workflowdienstzuordnung den Attributen eines Dienstvertrags zugeordnet werden.Ein Beispiel mit einer schrittweisen Anleitung zum Erstellen eines Vertrag zuerst\-Workflowdiensts finden Sie unter [Vorgehensweise: Erstellen eines Workflowdiensts zum Verarbeiten eines vorhandenen Dienstvertrags](../../../docs/framework/windows-workflow-foundation//how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md).  
  
## In diesem Thema  
  
-   [Zuordnen von Dienstvertragsattributen zu Workflowattributen](../../../docs/framework/windows-workflow-foundation//contract-first-workflow-service-development.md#MappingAttributes)  
  
    -   [Dienstvertragsattribute](../../../docs/framework/windows-workflow-foundation//contract-first-workflow-service-development.md#ServiceContract)  
  
    -   [Vorgangsvertragsattribute](../../../docs/framework/windows-workflow-foundation//contract-first-workflow-service-development.md#OperationContract)  
  
    -   [Nachrichtenvertragsattribute](../../../docs/framework/windows-workflow-foundation//contract-first-workflow-service-development.md#MessageContract)  
  
    -   [Datenvertragsattribute](../../../docs/framework/windows-workflow-foundation//contract-first-workflow-service-development.md#DataContract)  
  
    -   [Fehlervertragsattribute](../../../docs/framework/windows-workflow-foundation//contract-first-workflow-service-development.md#FaultContract)  
  
-   [Zusätzliche Support- und Implementierungsinformationen](../../../docs/framework/windows-workflow-foundation//contract-first-workflow-service-development.md#AdditionalSupport)  
  
    -   [Nicht unterstützte Dienstvertragsfunktionen](../../../docs/framework/windows-workflow-foundation//contract-first-workflow-service-development.md#UnsupportedFeatures)  
  
    -   [Generierung konfigurierter Messagingaktivitäten](../../../docs/framework/windows-workflow-foundation//contract-first-workflow-service-development.md#ActivityGeneration)  
  
##  <a name="MappingAttributes"></a> Zuordnen von Dienstvertragsattributen zu Workflowattributen  
 Die Tabellen in den folgenden Abschnitten enthalten die verschiedenen WCF\-Attribute und \-Eigenschaften und veranschaulichen die Zuordnung zu Messagingaktivitäten und Eigenschaften in einem Vertrag zuerst\-Workflow.  
  
-   [Dienstvertragsattribute](../../../docs/framework/windows-workflow-foundation//contract-first-workflow-service-development.md#ServiceContract)  
  
-   [Vorgangsvertragsattribute](../../../docs/framework/windows-workflow-foundation//contract-first-workflow-service-development.md#OperationContract)  
  
-   [Nachrichtenvertragsattribute](../../../docs/framework/windows-workflow-foundation//contract-first-workflow-service-development.md#MessageContract)  
  
-   [Datenvertragsattribute](../../../docs/framework/windows-workflow-foundation//contract-first-workflow-service-development.md#DataContract)  
  
-   [Fehlervertragsattribute](../../../docs/framework/windows-workflow-foundation//contract-first-workflow-service-development.md#FaultContract)  
  
###  <a name="ServiceContract"></a> Dienstvertragsattribute  
  
|Eigenschaftenname|Wird unterstützt|Beschreibung|WF\-Validierung|  
|-----------------------|----------------------|------------------|---------------------|  
|CallbackContract|Nein|Ruft den Typ des Rückrufvertrags ab oder legt ihn fest, wenn es sich beim Vertrag um einen Duplexvertrag handelt.|\(Nicht zutreffend\)|  
|ConfigurationName|Nein|Ruft den Namen ab, mit dem der Dienst in einer Anwendungskonfigurationsdatei gesucht wird, oder legt ihn fest.|\(Nicht zutreffend\)|  
|HasProtectionLevel|Ja|Ruft einen Wert ab, der angibt, ob dem Member eine Schutzebene zugewiesen wurde.|Receive.ProtectionLevel darf nicht NULL sein.|  
|Name|Ja|Ruft den Namen für das \<portType\>\-Element in Web Services Description Language \(WSDL\) ab oder legt diesen fest.|Receive.ServiceContractName.LocalName sollte übereinstimmen.|  
|Namespace|Ja|Ruft den Namespace des \<portType\>\-Elements in der Web Services Description Language \(WSDL\) ab oder legt diesen fest.|Receive.ServiceContractName.NameSpace sollte übereinstimmen.|  
|ProtectionLevel|Ja|Gibt an, ob die Vertragsbindung den Wert der ProtectionLevel\-Eigenschaft unterstützen muss.|Receive.ProtectionLevel sollte übereinstimmen.|  
|SessionMode|Nein|Ruft ab, ob Sitzungen zugelassen, nicht zugelassen oder erforderlich sind, oder legt dies fest.|\(Nicht zutreffend\)|  
|TypeId|Nein|Ruft bei der Implementierung in einer abgeleiteten Klasse einen eindeutigen Bezeichner für dieses Attribut ab.\(Vom Attribut geerbt\).|\(Nicht zutreffend\)|  
  
 Unterabschnittstext hier einfügen.  
  
###  <a name="OperationContract"></a> Vorgangsvertragsattribute  
  
|Eigenschaftenname|Wird unterstützt|Beschreibung|WF\-Validierung|  
|-----------------------|----------------------|------------------|---------------------|  
|Action|Ja|Ruft ab oder legt die WS\-Adressierungsaktion der Anforderungsnachricht fest.|Receive.Action sollte übereinstimmen.|  
|AsyncPattern|Nein|Gibt an, dass ein Vorgang mit dem Methodenpaar Begin\<methodName\> und End\<methodName\> in einem Dienstvertrag asynchron implementiert wird.|\(Nicht zutreffend\)|  
|HasProtectionLevel|Ja|Ruft einen Wert ab, der angibt, ob die Nachrichten für diesen Vorgang verschlüsselt oder signiert werden müssen oder beides.|Receive.ProtectionLevel darf nicht NULL sein.|  
|IsInitiating|Nein|Ruft einen Wert ab, der angibt, ob die Methode einen Vorgang implementiert, der eine Sitzung auf dem Server initiieren kann \(sofern eine solche Sitzung vorhanden ist\), oder legt diesen fest.|\(Nicht zutreffend\)|  
|IsOneWay|Ja|Ruft einen Wert ab, der angibt, ob ein Vorgang eine Antwortnachricht zurückgibt, oder legt diesen fest.|\(Kein SendReply für dieses Empfangsvorgang ODER kein ReceiveReply für diesen Sendevorgang\).|  
|IsTerminating|Nein|Ruft einen Wert ab, der angibt, ob der Dienstvorgang bewirkt, dass der Server die Sitzung schließt, nachdem die Antwortnachricht gesendet wurde.|\(Nicht zutreffend\)|  
|Name|Ja|Ruft den Namen des Vorgangs ab oder legt diesen fest.|Receive.OperationName sollte übereinstimmen.|  
|ProtectionLevel|Ja|Ruft einen Wert ab, der angibt, ob die Nachrichten eines Vorgangs verschlüsselt oder signiert werden müssen oder beides beziehungsweise legt ihn fest.|Receive.ProtectionLevel sollte übereinstimmen.|  
|ReplyAction|Ja|Ruft ab oder legt den Wert der SOAP\-Aktion für die Antwortnachricht des Vorgangs fest.|SendReply.Action sollte übereinstimmen.|  
|TypeId|Nein|Ruft bei der Implementierung in einer abgeleiteten Klasse einen eindeutigen Bezeichner für dieses Attribut ab.\(Vom Attribut geerbt\).|\(Nicht zutreffend\)|  
  
###  <a name="MessageContract"></a> Nachrichtenvertragsattribute  
  
|Eigenschaftenname|Wird unterstützt|Beschreibung|WF\-Validierung|  
|-----------------------|----------------------|------------------|---------------------|  
|HasProtectionLevel|Ja|Ruft einen Wert ab, der angibt, ob die Nachricht über eine Schutzebene verfügt.|Keine Validierung \(Receive.Content und SendReply.Content müssen mit dem Nachrichtenvertragstyp übereinstimmen\).|  
|IsWrapped|Ja|Ruft einen Wert ab oder legt einen Wert fest, der angibt, ob der Nachrichtentext über ein Wrapperelement verfügt.|Keine Validierung \(Receive.Content und Sendreply.Content müssen mit dem Nachrichtenvertragstyp übereinstimmen\).|  
|ProtectionLevel|Nein|Ruft einen Wert ab, der angibt, ob die Nachricht verschlüsselt oder signiert werden muss oder beides, oder legt diesen Wert fest.|\(Nicht zutreffend\)|  
|TypeId|Ja|Ruft bei der Implementierung in einer abgeleiteten Klasse einen eindeutigen Bezeichner für dieses Attribut ab.\(Vom Attribut geerbt\).|Keine Validierung \(Receive.Content und SendReply.Content müssen mit dem Nachrichtenvertragstyp übereinstimmen\).|  
|WrapperName|Ja|Ruft den Wrapperelementnamen des Nachrichtentexts ab, oder legt ihn fest.|Keine Validierung \(Receive.Content und SendReply.Content müssen mit dem Nachrichtenvertragstyp übereinstimmen\).|  
|WrapperNamespace|Nein|Ruft den Namespace des Nachrichtentext\-Wrapperelements ab oder legt ihn fest.|\(Nicht zutreffend\)|  
  
###  <a name="DataContract"></a> Datenvertragsattribute  
  
|Eigenschaftenname|Wird unterstützt|Beschreibung|WF\-Validierung|  
|-----------------------|----------------------|------------------|---------------------|  
|IsReference|Nein|Ruft einen Wert ab oder legt einen Wert fest, der angibt, ob Objektverweisdaten beizubehalten sind.|\(Nicht zutreffend\)|  
|Name|Ja|Ruft den Namen des Datenvertrags für den Typ ab oder legt ihn fest.|Keine Validierung \(Receive.Content und SendReply.Content müssen mit dem Nachrichtenvertragstyp übereinstimmen\).|  
|Namespace|Ja|Ruft den Namespace des Datenvertrags für den Typ ab oder legt ihn fest.|Keine Validierung \(Receive.Content und SendReply.Content müssen mit dem Nachrichtenvertragstyp übereinstimmen\).|  
|TypeId|Nein|Ruft bei der Implementierung in einer abgeleiteten Klasse einen eindeutigen Bezeichner für dieses Attribut ab.\(Vom Attribut geerbt\).|\(Nicht zutreffend\)|  
  
###  <a name="FaultContract"></a> Fehlervertragsattribute  
  
|Eigenschaftenname|Wird unterstützt|Beschreibung|WF\-Validierung|  
|-----------------------|----------------------|------------------|---------------------|  
|Action|Ja|Ruft die Aktion der SOAP\-Fehlernachricht ab, die als Bestandteil des Vorgangsvertrags angegeben wurde, oder legt sie fest.|SendReply.Action sollte übereinstimmen.|  
|DetailType|Ja|Ruft den Typ eines serialisierbaren Objekts ab, das Fehlerinformationen enthält.|SendReply.Content sollte dem Typ entsprechen.|  
|HasProtectionLevel|Nein|Ruft einen Wert ab, der angibt, ob der SOAP\-Fehlernachricht eine Sicherheitsebene zugewiesen wurde.|\(Nicht zutreffend\)|  
|Name|Nein|Ruft ab oder legt den Namen der Fehlernachricht in WSDL \(Web Services Description Language\) fest.|\(Nicht zutreffend\)|  
|Namespace|Nein|Ruft den Namespace des SOAP\-Fehlers ab oder legt diesen fest.|\(Nicht zutreffend\)|  
|ProtectionLevel|Nein|Gibt die Sicherheitsebene an, die der SOAP\-Fehler von der Bindung fordert.|\(Nicht zutreffend\)|  
|TypeId|Nein|Ruft bei der Implementierung in einer abgeleiteten Klasse einen eindeutigen Bezeichner für dieses Attribut ab.\(Vom Attribut geerbt\).|\(Nicht zutreffend\)|  
  
##  <a name="AdditionalSupport"></a> Zusätzliche Support\- und Implementierungsinformationen  
  
-   [Nicht unterstützte Dienstvertragsfunktionen](../../../docs/framework/windows-workflow-foundation//contract-first-workflow-service-development.md#UnsupportedFeatures)  
  
-   [Generierung konfigurierter Messagingaktivitäten](../../../docs/framework/windows-workflow-foundation//contract-first-workflow-service-development.md#ActivityGeneration)  
  
###  <a name="UnsupportedFeatures"></a> Nicht unterstützte Dienstvertragsfunktionen  
  
-   Die Verwendung von TPL \(Task Parallel Library\)\-Tasks in den Verträgen wird nicht unterstützt.  
  
-   Die Vererbung in Dienstverträgen wird nicht unterstützt.  
  
###  <a name="ActivityGeneration"></a> Generierung konfigurierter Messagingaktivitäten  
 Zwei öffentliche statische Methoden werden der <xref:System.ServiceModel.Activities.Receive>\-Aktivität und der <xref:System.ServiceModel.Activities.SendReply>\-Aktivität hinzugefügt, um bei Verwendung von Vertrag zuerst\-Workflowdiensten die Generierung von vorkonfigurierten Nachrichtenaktivitäten zu unterstützen.  
  
-   <xref:System.ServiceModel.Activities.Receive.FromOperationDescription%2A?displayProperty=fullName>  
  
-   <xref:System.ServiceModel.Activities.SendReply.FromOperationDescription%2A?displayProperty=fullName>  
  
 Die Aktivität, die durch diese Methoden generiert wird, sollte die Vertragsüberprüfung erfolgreich abschließen. Daher werden diese Methoden intern als Teil der Validierungslogik für <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply> verwendet.<xref:System.ServiceModel.Activities.Receive.OperationName%2A>, <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>, <xref:System.ServiceModel.Activities.Receive.Action%2A>, <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>, <xref:System.ServiceModel.Activities.Receive.ProtectionLevel%2A> und <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> werden alle vorkonfiguriert, um dem importierten Vertrag zu entsprechen.Im Workflow\-Designer werden die Abschnitte **Meldung** oder **Parameter** auf der Seite für Inhaltseigenschaften ebenfalls vorkonfiguriert, damit sie dem Vertrag entsprechen.  
  
 WCF\-Fehlerverträge werden auch behandelt, indem eine separate Gruppe konfigurierter <xref:System.ServiceModel.Activities.SendReply>\-Aktivitäten für jeden Fehler zurückgegeben wird, der in <xref:System.ServiceModel.Description.OperationDescription.Faults%2A> <xref:System.ServiceModel.Description.FaultDescriptionCollection> angezeigt wird.  
  
 Bei anderen Teilen von <xref:System.ServiceModel.Description.OperationDescription>, die von WF\-Diensten derzeit noch nicht unterstützt werden \(z. B.WebGet\-\/WebInvoke\-Verhaltensweisen oder Verhaltensweisen benutzerdefinierter Vorgänge\) werden diese Werte bei der Generierung und Konfiguration von der API ignoriert.Es werden keine Ausnahmen ausgelöst.