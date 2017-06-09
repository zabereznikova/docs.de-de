---
title: "Datenvertragsnamen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
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
  - "Datenverträge [WCF], Benennen"
ms.assetid: 31f87e6c-247b-48f5-8e94-b9e1e33d8d09
caps.latest.revision: 27
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 27
---
# Datenvertragsnamen
Zuweilen verfügen Client und Dienst nicht über dieselben Typen.Sie können jedoch Daten austauschen, wenn die Datenverträge auf beiden Seiten gleich sind.[Datenvertragsäquivalenz](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md) basiert auf Datenvertrags\- und Datenmembernamen, und daher wird ein Mechanismus bereitgestellt, der diesen Namen Typen und Member zuordnet.In diesem Thema werden die Regeln für die Namensgebung von Datenverträgen sowie das Standardverhalten der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Infrastruktur bei der Namenserstellung erläutert.  
  
## Grundregeln  
 Zu den Grundregeln bei der Namensvergabe von Datenverträgen gehören:  
  
-   Ein vollständig qualifizierter Datenvertragsname besteht aus einem Namespace und einem Namen.  
  
-   Datenelemente verfügen nur über Namen, aber nicht über Namespaces.  
  
-   Bei der Verarbeitung von Datenverträgen unterscheidet die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Infrastruktur bei den Namespaces, den Namen der Datenverträge und den Datenelementen zwischen Groß\- und Kleinschreibung.  
  
## Datenvertragsnamespaces  
 Ein Datenvertragsnamespace nimmt die Form eines URI \(Uniform Resource Identifiers\) an.Der URI kann entweder absolut oder relativ sein.Standardmäßig wird Datenverträgen eines bestimmten Typs ein Namespace zugeordnet, der aus dem Namespace der CLR \(Common Language Runtime\) desselben Typs resultiert.  
  
 Standardmäßig wird jeder beliebige CLR\-Namespace \(im Format *Clr.Namespace*\) dem Namespace "http:\/\/schemas.datacontract.org\/2004\/07\/Clr.Namespace" zugeordnet.Um diesen Standard zu überschreiben, übernehmen Sie das <xref:System.Runtime.Serialization.ContractNamespaceAttribute>\-Attribut für das ganze Modul oder die Assembly.Alternativ können Sie den Datenvertragsnamespace für jeden Typ kontrollieren, indem Sie die <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A>\-Eigenschaft des <xref:System.Runtime.Serialization.DataContractAttribute> festlegen.  
  
> [!NOTE]
>  Der "http:\/\/schemas.microsoft.com\/2003\/10\/Serialization\-"Namespace wird reserviert und kann nicht als Datenvertragsnamespace verwendet werden.  
  
> [!NOTE]
>  Sie können den Standardnamespace nicht in Datenvertragstypen überschreiben, die `delegate`\-Deklarationen enthalten.  
  
## Datenvertragsnamen  
 Der Standardname eines Datenvertrags für einen gegebenen Typ ist der Name des Typs.Um diesen Standard zu überschreiben, legen Sie die <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A>\-Eigenschaft auf dem <xref:System.Runtime.Serialization.DataContractAttribute> auf einen alternativen Namen fest.Besondere Regeln für generische Typen werden weiter unten in diesem Thema unter "Datenvertragsnamen für generische Typen" beschrieben.  
  
## Datenelementnamen  
 Der Standardname eines Datenelements für ein gegebenes Feld oder eine gegebene Eigenschaft ist der Name des Felds oder der Eigenschaft.Um diesen Standard zu überschreiben, legen Sie die <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A>\-Eigenschaft des <xref:System.Runtime.Serialization.DataMemberAttribute> auf einen alternativen Wert fest.  
  
### Beispiele  
 Das folgende Beispiel zeigt, wie Sie das Standardbenennungsverhalten für Datenverträge und Datenelemente überschreiben können.  
  
 [!code-csharp[C_DataContractNames#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#1)]
 [!code-vb[C_DataContractNames#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#1)]  
  
## Datenvertragsnamen für generische Typen  
 Für die Bestimmung von Datenvertragsnamen für generische Typen existieren besondere Regeln.Diese Regeln helfen, Übereinstimmungen von Datenvertragsnamen zwischen zwei geschlossenen Generika des gleichen generischen Typs zu vermeiden.  
  
 Standardmäßig ist der Datenvertragsname eines generischen Typs der Name des Typs, gefolgt von der Zeichenfolge "Of", gefolgt von den Datenvertragsnamen der generischen Parameter, gefolgt von einem *Hash* und errechnet mithilfe der Datenvertragsnamespaces der generischen Parameter.Ein Hash ist das Ergebnis einer mathematischen Funktion, die als "Fingerabdruck" fungiert, der Daten eindeutig identifiziert.Wenn es sich bei allen generischen Parametern um primitive Typen handelt, wird der Hash weggelassen.  
  
 Betrachten Sie beispielsweise die Typen im folgenden Beispiel:  
  
 [!code-csharp[C_DataContractNames#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#2)]
 [!code-vb[C_DataContractNames#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#2)]  
  
 In diesem Beispiel hat der Typ `Drawing<Square,RegularRedBrush>` den Datenvertragsnamen "DrawingOfSquareRedBrush5HWGAU6h", wobei "5HWGAU6h" ein Hash der Namespaces "urn:shapes" und "urn:default" ist.Der Typ `Drawing<Square,SpecialRedBrush>` hat den Datenvertragsnamen "DrawingOfSquareRedBrushjpB5LgQ\_S", wobei "jpB5LgQ\_S" ein Hash der Namespaces "urn:shapes" und "urn:special" ist.Beachten Sie, dass die beiden Namen bei Nichtverwendung des Hashes identisch sind und daher ein Namenskonflikt auftritt.  
  
## Anpassen von Datenvertragsnamen für generische Typen  
 Zuweilen sind die für generische Typen erstellten Datenvertragsnamen, wie zuvor beschrieben, nicht akzeptabel.Beispielsweise können Sie von vornherein wissen, dass eine Übereinstimmung der Namen ausgeschlossen ist, und möchten daher den Hash entfernen.In diesem Fall können Sie die <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A>\-Eigenschaft des `DataContractAttribute`\-Attributs nutzen, um eine andere Art der Erstellung der Namen festzulegen.Sie können Zahlen in geschweiften Klammern innerhalb der `Name`\-Eigenschaft nutzen, um auf Datenvertragsnamen von generischen Parametern zu verweisen.\(0 \(null\) verweist auf den ersten Parameter, 1 verweist auf den zweiten usw.\) Um auf den Hash zu verweisen, können Sie ein Rautezeichen \(\#\) in geschweiften Klammern verwenden.Sie können jeden dieser Verweise mehrmals oder gar nicht verwenden.  
  
 Beispielsweise könnte der vorangehende allgemeine `Drawing`\-Typ deklariert worden sein, wie im folgenden Beispiel gezeigt:  
  
 [!code-csharp[c_DataContractNames#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#3)]
 [!code-vb[c_DataContractNames#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#3)]  
  
 In diesem Fall hat der Typ `Drawing<Square,RegularRedBrush>` den Datenvertragsnamen "Drawing\_using\_RedBrush\_brush\_and\_Square\_shape".Beachten Sie, dass der Hash aufgrund des "{\#}" in der <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A>\-Eigenschaft nicht Teil des Namens ist und der Typ somit einer Benennungsübereinstimmung unterliegen kann. Beispielsweise hätte der Typ `Drawing<Square,SpecialRedBrush>` den gleichen Datenvertragsnamen.  
  
## Siehe auch  
 <xref:System.Runtime.Serialization.DataContractAttribute>   
 <xref:System.Runtime.Serialization.DataMemberAttribute>   
 <xref:System.Runtime.Serialization.ContractNamespaceAttribute>   
 [Verwenden von Datenverträgen](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)   
 [Datenvertragsäquivalenz](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)   
 [Data Contract Names](../../../../docs/framework/wcf/feature-details/data-contract-names.md)   
 [Datenvertragsversionsverwaltung](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md)