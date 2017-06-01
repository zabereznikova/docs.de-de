---
title: "ServiceModel-Attribute und ServiceDescription-Referenz | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4ab86b17-eab9-4846-a881-0099f9a7cc64
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# ServiceModel-Attribute und ServiceDescription-Referenz
Die *Beschreibungsstruktur* ist die Hierarchie der Typen \(angefangen bei der Klasse <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=fullName>\), die zusammen jeden Aspekt eines Diensts beschreiben.[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verwendet eine Beschreibungsstruktur zur Erstellung einer gültigen Dienstlaufzeit, um Web Services Description Language \(WSDL\), XML Schema\-Definitionssprache \(XSD\) und Policy\-Aussagen \(Metadaten\) über den Dienst zu veröffentlichen, die Clients verwenden können, um sich mit dem Dienst zu verbinden und ihn zu nutzen, und um verschiedene Code\- und Konfigurationsdateirepräsentationen der Beschreibungsstrukturwerte zu generieren.  
  
 Dieses Thema beschreibt, wie vertragsbezogene Eigenschaften aus dem Dienstvertrag abgerufen, wie sie implementiert und der Beschreibungsstruktur hinzugefügt werden.In einigen Fällen werden Attributwerte in Verhaltenseigenschaften umgewandelt, und das Verhalten wird dann in die Beschreibungsstruktur eingefügt.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Konvertierung der Beschreibungsstrukturwerte in Metadaten finden Sie unter [ServiceDescription und WSDL\-Verweis](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md).  
  
## Zuordnen von Vorgängen zur Beschreibungsstruktur  
 In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Anwendungen werden Dienstverträge nach Schnittstellen \(oder Klassen\) erstellt, die Attribute verwenden, um die Schnittstelle oder Klasse und ihre Methoden als eine Vorgangsgruppierung zu markieren.Wenn eine <xref:System.ServiceModel.ServiceHost>\-Klasse geöffnet ist, werden Dienstverträge und Implementierungen immer wieder reflektiert und mit den Konfigurationsinformationen in eine Beschreibungsstruktur zusammengeführt.  
  
 Es gibt zwei Typen von Vorgangsmodellen: das *Parametermodell* und das *Nachrichtenvertragsmodell*.Das Parametermodell verwendet verwaltete Methoden, die keinen Parameter oder Rückgabewerttyp besitzen, der von der Klasse <xref:System.ServiceModel.MessageContractAttribute?displayProperty=fullName> markiert wird.In diesem Modell kontrollieren die Entwickler die Serialisierung der Parameter und Rückgabewerte, aber [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert die Werte, die verwendet werden, um die Beschreibungsstruktur für den Dienst und seinen Vertrag zu füllen.  
  
 In Konfigurationsdateien angegebene Bindungen werden direkt in die Eigenschaft <xref:System.ServiceModel.Description.ServiceEndpoint.Binding%2A?displayProperty=fullName> geladen.  
  
|ServiceBehaviorAttribute\-Eigenschaft|Beschreibungsstrukturwert beeinflusst|  
|-------------------------------------------|-------------------------------------------|  
|Name|<xref:System.ServiceModel.Description.ServiceDescription.Name%2A>|  
|Namespace|<xref:System.ServiceModel.Description.ServiceDescription.Namespace%2A>|  
|ConfigurationName|<xref:System.ServiceModel.Description.ServiceDescription.ConfigurationName%2A>|  
|IgnoreExtensionDataObject|Legt die Eigenschaft <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.IgnoreExtensionDataObject%2A> für alle Vorgänge fest.|  
|MaxItemsInObjectGraph|Legt die Eigenschaft <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.MaxItemsInObjectGraph%2A> für alle Vorgänge fest.|  
  
|ServiceContractAttribute\-Eigenschaft|Beschreibungsstrukturwert beeinflusst|  
|-------------------------------------------|-------------------------------------------|  
|CallbackContract|<xref:System.ServiceModel.Description.ContractDescription.CallbackContractType%2A>, <xref:System.ServiceModel.Description.MessageDescription> hat allen Operationen <xref:System.ServiceModel.Description.OperationDescription.Messages%2A> hinzugefügt.|  
|ConfigurationName|<xref:System.ServiceModel.Description.ContractDescription.ConfigurationName%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.ContractDescription.ProtectionLevel%2A> und möglicherweise untergeordnete Schutzebenen.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Schutzebenenhierarchie finden Sie unter [Grundlagen der Schutzebene](../../../../docs/framework/wcf/understanding-protection-level.md).|  
|SessionMode|<xref:System.ServiceModel.Description.ContractDescription.SessionMode%2A>|  
  
|ServiceKnownTypesAttribute\-Wert|Beschreibungsstrukturwert beeinflusst|  
|--------------------------------------|-------------------------------------------|  
|MethodName|<xref:System.ServiceModel.Description.OperationDescription.KnownTypes%2A>|  
  
|OperationContractAttribute\-Wert|Beschreibungsstrukturwert beeinflusst|  
|--------------------------------------|-------------------------------------------|  
|Aktion|<xref:System.ServiceModel.Description.MessageDescription.Action%2A> für die Ausgabe\- oder Eingabenachricht, abhängig vom Vertrag\/Rückrufvertrag.|  
|AsyncPattern|Wenn "true", <xref:System.ServiceModel.Description.OperationDescription.BeginMethod%2A> und <xref:System.ServiceModel.Description.OperationDescription.EndMethod%2A>|  
|IsOneWay|Wird einer einzelnen <xref:System.ServiceModel.Description.MessageDescription> in <xref:System.ServiceModel.Description.OperationDescription.Messages%2A> zugeordnet|  
|IsInitiating|<xref:System.ServiceModel.Description.OperationDescription.IsInitiating%2A>|  
|IsTerminating|<xref:System.ServiceModel.Description.OperationDescription.IsTerminating%2A>|  
|Name|<xref:System.ServiceModel.Description.OperationDescription.Name%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.OperationDescription.ProtectionLevel%2A> und möglicherweise untergeordnete Schutzebenen.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Schutzebenenhierarchie finden Sie unter [Grundlagen der Schutzebene](../../../../docs/framework/wcf/understanding-protection-level.md).|  
|ReplyAction|<xref:System.ServiceModel.Description.MessageDescription.Action%2A> für die Ausgabe\- oder Eingabenachricht, abhängig vom Vertrag\/Rückrufvertrag.|  
  
|FaultContractAttribute\-Wert|Beschreibungsstrukturwert beeinflusst|  
|----------------------------------|-------------------------------------------|  
|Action|<xref:System.ServiceModel.Description.FaultDescription.Action%2A>, abhängig vom Vertrag\/Rückrufvertrag.|  
|DetailType|<xref:System.ServiceModel.Description.FaultDescription.DetailType%2A>|  
|Name|<xref:System.ServiceModel.Description.FaultDescription.Name%2A>|  
|Namespace|<xref:System.ServiceModel.Description.FaultDescription.Namespace%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.FaultDescription.ProtectionLevel%2A>|  
  
|DataContractFormatAttribute\-Wert|Beschreibungsstrukturwert beeinflusst|  
|---------------------------------------|-------------------------------------------|  
|Verwendung|Der Wert <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> ist auf <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> für den Vorgang festgelegt.|  
  
|XmlSerializerFormatAttribute\-Wert|Beschreibungsstrukturwert beeinflusst|  
|----------------------------------------|-------------------------------------------|  
|Style|Diese <xref:System.ServiceModel.XmlSerializerFormatAttribute>\-Eigenschaft ist auf <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> für den Vorgang festgelegt.|  
|Use|<xref:System.ServiceModel.XmlSerializerFormatAttribute> ist auf <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> für den Vorgang festgelegt.|  
  
|TransactionFlowAttribute\-Wert|Beschreibungsstrukturwert beeinflusst|  
|------------------------------------|-------------------------------------------|  
|TransactionFlowOption|<xref:System.ServiceModel.TransactionFlowAttribute> wird der Eigenschaft <xref:System.ServiceModel.Description.OperationDescription.Behaviors%2A> als Vorgangsverhalten hinzugefügt.|  
  
|MessageContractAttribute\-Wert|Beschreibungsstrukturwert beeinflusst|  
|------------------------------------|-------------------------------------------|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessageDescription.ProtectionLevel%2A>|  
|WrapperName|<xref:System.ServiceModel.Description.MessageBodyDescription.WrapperName%2A>|  
|WrapperNamespace|<xref:System.ServiceModel.Description.MessageBodyDescription.WrapperNamespace%2A>|  
  
|MessageHeaderAttribute\-Wert|Beschreibungsstrukturwert beeinflusst|  
|----------------------------------|-------------------------------------------|  
|Akteur|<xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A> für den entsprechenden Header in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|MustUnderstand|<xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A> für den entsprechenden Header in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Name|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A> für den entsprechenden Header in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Namespace|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A> für den entsprechenden Header in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A> für den entsprechenden Header in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Relay|<xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A> für den entsprechenden Header in <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
  
|MessageBodyMemberAttribute\-Wert|Beschreibungsstrukturwert beeinflusst|  
|--------------------------------------|-------------------------------------------|  
|Name|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A> für den entsprechenden Teil in <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|Namespace|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A> für den entsprechenden Teil in <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|Reihenfolge|<xref:System.ServiceModel.Description.MessagePartDescription.Index%2A> für den entsprechenden Teil in <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A> für den entsprechenden Teil in <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
  
|MessageHeaderArrayAttribute\-Wert|Beschreibungsstrukturwert beeinflusst|  
|---------------------------------------|-------------------------------------------|  
|Akteur|<xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A>|  
|MustUnderstand|<xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A>|  
|Name|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>|  
|Namespace|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A>|  
|Relay|<xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A>|  
  
|MessagePropertyAttribute\-Wert|Beschreibungsstrukturwert beeinflusst|  
|------------------------------------|-------------------------------------------|  
|Name|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>|  
  
|MessageParameterAttribute\-Wert|Beschreibungsstrukturwert beeinflusst|  
|-------------------------------------|-------------------------------------------|  
|Name|<xref:System.ServiceModel.Description.MessagePartDescription.name%2A> für den entsprechenden Teil in <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Konvertierung der Beschreibungsstrukturwerte in Metadaten finden Sie unter [ServiceDescription und WSDL\-Verweis](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md).  
  
## Siehe auch  
 [ServiceDescription und WSDL\-Verweis](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md)