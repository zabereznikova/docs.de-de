---
title: Enumerationstypen in Datenverträgen
description: Erfahren Sie, wie das Daten Vertragsmodell Enumerationen als Teil des WFC-Programmiermodells ausdrückt.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], enumeration types
ms.assetid: b5d694da-68cb-4b74-a5fb-75108a68ec3b
ms.openlocfilehash: ff3184a285e88d47d4545a38a6c74b2f209827fb
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247298"
---
# <a name="enumeration-types-in-data-contracts"></a>Enumerationstypen in Datenverträgen
Enumerationen können im Datenvertragsmodell ausgedrückt werden. In diesem Thema werden mehrere Beispiele behandelt, in denen das Programmiermodell erklärt wird.  
  
## <a name="enumeration-basics"></a>Grundlagen der Enumeration  
 Eine Möglichkeit, Enumerationstypen im Datenvertragmodell zu verwenden, besteht darin, das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut auf den Typ anzuwenden. Anschließend müssen Sie das <xref:System.Runtime.Serialization.EnumMemberAttribute>-Attribut auf jeden Member anwenden, der im Datenvertrag enthalten sein soll.  
  
 Das folgende Beispiel zeigt zwei Klassen. Die erste Klasse verwendet die Enumeration, und die zweite Klasse definiert die Enumeration.  
  
 [!code-csharp[c_DataContractEnumerations#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#1)]
 [!code-vb[c_DataContractEnumerations#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#1)]  
  
 Sie können eine Instanz der `Car`-Klasse nur senden oder empfangen, wenn das Feld `condition` auf einen der folgenden Werte festgelegt ist: `New`, `Used` oder `Rental`. Wenn `condition` den Wert `Broken` oder `Stolen` hat, wird eine <xref:System.Runtime.Serialization.SerializationException> ausgelöst.  
  
 Sie können die <xref:System.Runtime.Serialization.DataContractAttribute>-Eigenschaften (<xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> und <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A>) wie gewohnt für Enumerationsdatenverträge verwenden.  
  
### <a name="enumeration-member-values"></a>Enumerationsmemberwerte  
 Im Allgemeinen enthält der Datenvertrag Enumerationsmembernamen, keine numerischen Werte. Wenn jedoch das Daten Vertragsmodell verwendet wird, wenn es sich bei der Empfangsseite um einen WCF-Client handelt, werden die numerischen Werte vom exportierten Schema beibehalten. Beachten Sie, dass dies nicht der Fall ist, wenn mit der [XmlSerializer-Klasse](using-the-xmlserializer-class.md)verwendet wird.  
  
 Wenn im obigen Beispiel `condition` auf `Used` festgelegt ist und die Daten in XML serialisiert werden, lautet das XML-Ergebnis `<condition>Used</condition>``<condition>1</condition>`, und nicht . Deshalb entspricht der folgende Datenvertrag dem Datenvertrag von `CarConditionEnum`.  
  
 [!code-csharp[c_DataContractEnumerations#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#2)]
 [!code-vb[c_DataContractEnumerations#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#2)]  
  
 Sie können beispielsweise `CarConditionEnum` auf der Absenderseite und `CarConditionWithNumbers` auf der Empfängerseite verwenden. Obwohl die Absenderseite den Wert 1 und die Empfängerseite den Wert 20 für `Used` verwendet, lautet die XML-Darstellung für beide Seiten `<condition>Used</condition>`.  
  
 Um das Einbinden in den Datenvertrag zu erreichen, müssen Sie das <xref:System.Runtime.Serialization.EnumMemberAttribute>-Attribut anwenden. In der .NET Framework können Sie immer den besonderen Wert 0 (null) auf eine Enumeration anwenden, bei der es sich auch um den Standardwert für eine beliebige Enumeration handelt. Auch dieser Sonderwert 0 kann jedoch nur serialisiert werden, wenn er mithilfe des <xref:System.Runtime.Serialization.EnumMemberAttribute>-Attributs gekennzeichnet ist.  
  
 Dabei gelten zwei Ausnahmen:  
  
- Flagenumerationen (weiter unten in diesem Thema beschrieben).  
  
- Enumerationsdatenmember, für die die <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>-Eigenschaft auf `false` festgelegt ist. (In diesem Fall wird die Enumeration mit dem Wert "0" einfach aus den serialisierten Daten weggelassen.)  
  
### <a name="customizing-enumeration-member-values"></a>Anpassen von Enumerationsmemberwerten  
 Sie können den Enumerationsmemberwert anpassen, der Teil des Datenvertrags ist, indem Sie die <xref:System.Runtime.Serialization.EnumMemberAttribute.Value%2A>-Eigenschaft des <xref:System.Runtime.Serialization.EnumMemberAttribute>-Attributs verwenden.  
  
 Der folgende Datenvertrag entspricht auch dem Datenvertrag von `CarConditionEnum`.  
  
 [!code-csharp[c_DataContractEnumerations#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#3)]
 [!code-vb[c_DataContractEnumerations#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#3)]  
  
 Nach der Serialisierung weist der Wert von `PreviouslyOwned` die XML-Darstellung `<condition>Used</condition>` auf.  
  
## <a name="simple-enumerations"></a>Einfache Enumerationen  
 Sie können auch Enumerationstypen serialisieren, auf die das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut nicht angewendet wurde. Enumerationstypen dieser Art werden exakt wie zuvor beschrieben behandelt. Es gilt jedoch die Ausnahme, dass jeder Member (auf den das <xref:System.NonSerializedAttribute>-Attribut nicht angewendet wurde) so behandelt wird, als ob das <xref:System.Runtime.Serialization.EnumMemberAttribute>-Attribut angewendet wurde. Zum Beispiel verfügt die folgende Enumeration implizit über einen Datenvertrag, der dem Datenvertrag im vorherigen `CarConditionEnum`-Beispiel entspricht.  
  
 [!code-csharp[c_DataContractEnumerations#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#6)]
 [!code-vb[c_DataContractEnumerations#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#6)]  
  
 Sie können einfache Enumerationen verwenden, wenn es nicht erforderlich ist, den Datenvertragsnamen und den Namespace der Enumeration und die Enumerationsmemberwerte anzupassen.  
  
#### <a name="notes-on-simple-enumerations"></a>Hinweise zu einfachen Enumerationen  
 Wenn Sie das <xref:System.Runtime.Serialization.EnumMemberAttribute>-Attribut auf einfache Enumerationen anwenden, hat dies keine Auswirkung.  
  
 Es ist unerheblich, ob Sie das <xref:System.SerializableAttribute>-Attribut auf die Enumeration anwenden.  
  
 Die Tatsache, dass die <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse das <xref:System.NonSerializedAttribute>-Attribut berücksichtigt, das auf Enumerationsmember angewendet wird, gilt nicht für das Verhalten von <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> und <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>. Beide Serialisierungsprogramme ignorieren das <xref:System.NonSerializedAttribute>-Attribut.  
  
## <a name="flag-enumerations"></a>Flagenumerationen  
 Sie können das <xref:System.FlagsAttribute>-Attribut auf Enumerationen anwenden. In diesem Fall kann eine Liste von null oder mehr Enumerationswerten gleichzeitig gesendet oder empfangen werden.  
  
 Wenden Sie dazu das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut auf die Flagenumeration an, und markieren Sie dann alle Member, die Potenzen von 2 sind, mit dem <xref:System.Runtime.Serialization.EnumMemberAttribute>-Attribut. Beachten Sie, dass es sich bei der Progression um eine ununterbrochene Folge mit Potenzen des Werts 2 handeln muss (beispielsweise 1, 2, 4, 8, 16, 32, 64).  
  
 Die folgenden Schritte gelten für das Senden des Enumerationswerts eines Flags:  
  
1. Versuchen Sie, einen Enumerationsmember zu finden (mit angewendetem <xref:System.Runtime.Serialization.EnumMemberAttribute>-Attribut), der dem numerischen Wert zugeordnet ist. Wenn Sie einen Member finden, senden Sie eine Liste, die nur diesen Member enthält.  
  
2. Versuchen Sie, den numerischen Wert so zu einer Summe aufzulösen, dass Enumerationsmember vorhanden sind (jeweils mit angewendetem <xref:System.Runtime.Serialization.EnumMemberAttribute>-Attribut), die den einzelnen Teilen der Summe zugeordnet sind. Senden Sie die Liste mit allen Membern dieser Art. Beachten Sie, dass der *gierige Algorithmus* verwendet wird, um eine solche Summe zu finden. Daher besteht keine Garantie dafür, dass eine solche Summe gefunden wird, auch wenn Sie vorhanden ist. Um dieses Problem zu verhindern, sollten Sie sicherstellen, dass es sich bei den numerischen Werten der Enumerationsmember um Potenzen von 2 handelt.  
  
3. Lösen Sie eine <xref:System.Runtime.Serialization.SerializationException> aus, wenn die vorausgehenden zwei Schritte fehlschlagen und der numerische Wert ungleich 0 ist. Senden Sie die leere Liste, wenn der numerische Wert 0 ist.  
  
### <a name="example"></a>Beispiel  
 Das folgende Enumerationsbeispiel kann für einen Flagvorgang verwendet werden.  
  
 [!code-csharp[c_DataContractEnumerations#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#4)]
 [!code-vb[c_DataContractEnumerations#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#4)]  
  
 Die folgenden Beispielwerte werden dabei wie angegeben serialisiert.  
  
 [!code-csharp[c_DataContractEnumerations#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#5)]
 [!code-vb[c_DataContractEnumerations#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#5)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [Verwenden von Datenverträgen](using-data-contracts.md)
- [Angeben von Datenübertragung in Dienstverträgen](specifying-data-transfer-in-service-contracts.md)
