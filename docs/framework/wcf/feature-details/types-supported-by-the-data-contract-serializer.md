---
title: Vom Datenvertragsserialisierer unterstützte Typen
ms.date: 03/30/2017
helpviewer_keywords:
- serialization [WCF], supported types
ms.assetid: 7381b200-437a-4506-9556-d77bf1bc3f34
ms.openlocfilehash: f3eedda6c9493688680099f4b07810aebf69ff8a
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249460"
---
# <a name="types-supported-by-the-data-contract-serializer"></a>Vom Datenvertragsserialisierer unterstützte Typen

Windows Communication Foundation (WCF) verwendet das <xref:System.Runtime.Serialization.DataContractSerializer> standardmäßige Serialisierungsmodul, um Daten in XML zu konvertieren und XML wieder in Daten zu konvertieren. <xref:System.Runtime.Serialization.DataContractSerializer> ist für die Serialisierung von *Datenvertragstypen* konzipiert. Es unterstützt jedoch viele andere Typen, die Sie sich als Typen mit einem impliziten Datenvertrag vorstellen können. Die folgende Liste enthält alle Typen, die serialisiert werden können:

- Alle öffentlich sichtbaren Typen, die über einen Konstruktor ohne Parameter verfügen.

- Datenvertragstypen. Hierbei handelt es sich um Typen, auf die das <xref:System.Runtime.Serialization.DataContractAttribute> -Attribut angewendet wurde. Neue benutzerdefinierte Typen, die Geschäftsobjekte darstellen, sollten normalerweise als Datenvertragstypen erstellt werden. Weitere Informationen finden Sie unter [Verwenden von Datenverträgen](../../../../docs/framework/wcf/feature-details/using-data-contracts.md) und [serialisierbaren Typen](../../../../docs/framework/wcf/feature-details/serializable-types.md).

- Auflistungstypen. Hierbei handelt es sich um Typen, die Datenlisten darstellen. Diese Typen können reguläre Arrays von Typen oder Auflistungstypen sein, z.&#160;B. <xref:System.Collections.ArrayList> und <xref:System.Collections.Generic.Dictionary%602>. Das <xref:System.Runtime.Serialization.CollectionDataContractAttribute> -Attribut kann verwendet werden, um die Serialisierung dieser Typen anzupassen, es ist jedoch nicht erforderlich. Weitere Informationen finden Sie [unter Sammlungstypen in Datenverträgen](../../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md).

- Enumerationstypen. Enumerationen, einschließlich Flagenumerationen, sind serialisierbar. Optional können Enumerationstypen mit dem <xref:System.Runtime.Serialization.DataContractAttribute> -Attribut gekennzeichnet werden. In diesem Fall muss jeder Member, der an der Serialisierung teilnimmt, mit dem <xref:System.Runtime.Serialization.EnumMemberAttribute> -Attribut gekennzeichnet sein. Nicht gekennzeichnete Member werden nicht serialisiert. Weitere Informationen finden Sie unter [Enumerationstypen in Datenverträgen](../../../../docs/framework/wcf/feature-details/enumeration-types-in-data-contracts.md).

- Primitive Typen von .NET&#160;Framework. Die folgenden in .NET&#160;Framework integrierten Typen sind serialisierbar und werden als primitive Typen betrachtet: <xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Boolean>, <xref:System.Char>, <xref:System.Decimal>, <xref:System.Object>und <xref:System.String>.

- Andere primitive Typen. Diese Typen sind in .NET&#160;Framework keine primitiven Typen, werden im serialisierten XML-Formular jedoch als primitive Typen behandelt. Diese Typen sind <xref:System.DateTime>, <xref:System.DateTimeOffset>, <xref:System.TimeSpan>, <xref:System.Guid>, <xref:System.Uri>, <xref:System.Xml.XmlQualifiedName>sowie Arrays von <xref:System.Byte>.

  > [!NOTE]
  > Im Gegensatz zu anderen primitiven Typen ist <xref:System.DateTimeOffset> standardmäßig kein bekannter Typ. Weitere Informationen finden Sie unter [Bekannte Datenvertragstypen](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)).

- Mit dem <xref:System.SerializableAttribute> -Attribut gekennzeichnete Typen. Viele Typen, die in der .NET Framework-Basisklassenbibliothek enthalten sind, fallen in diese Kategorie. <xref:System.Runtime.Serialization.DataContractSerializer> unterstützt dieses Serialisierungs-Programmiermodell, das von .NET&#160;Framework-Remoting verwendet wurde, sowie <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>und <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>nicht nur vollständig, sondern bietet darüber hinaus Unterstützung für die <xref:System.Runtime.Serialization.ISerializable> -Schnittstelle.

- Typen, die UNformatiertes XML darstellen, oder Typen, die ADO.NET relationalen Daten darstellen. <xref:System.Xml.XmlElement> und das Array von <xref:System.Xml.XmlNode> -Typen werden als Methoden unterstützt, um XML direkt darzustellen. Außerdem werden Typen unterstützt, die die <xref:System.Xml.Serialization.IXmlSerializable> -Schnittstelle implementieren, einschließlich dem zugehörigen <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> -Attribut sowie dem <xref:System.Xml.Linq.XDocument> -Typ und dem <xref:System.Xml.Linq.XElement> -Typ. Der<xref:System.Data.DataTable> ADO.NET Typ <xref:System.Data.DataSet> und der Typ (sowie seine typisierten <xref:System.Xml.Serialization.IXmlSerializable> abgeleiteten Klassen) implementieren alle die Schnittstelle und passen daher in diese Kategorie. Weitere Informationen finden Sie unter [XML und ADO.NET Typen in Datenverträgen](../../../../docs/framework/wcf/feature-details/xml-and-ado-net-types-in-data-contracts.md).

## <a name="limitations-of-using-certain-types-in-partial-trust-mode"></a>Einschränkungen bei der Verwendung bestimmter Typen im teilweise vertrauenswürdigen Modus

In der folgenden Liste sind die Einschränkungen aufgeführt, die bei Verwendung bestimmter Typen in Szenarien im teilweise vertrauenswürdigen Modus gelten:

- Zum Serialisieren oder Deserialisieren eines Typs, der <xref:System.Runtime.Serialization.ISerializable> in teilweise vertrauenswürdigem Code mithilfe des <xref:System.Runtime.Serialization.DataContractSerializer> implementiert, sind die <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter%2A> -Berechtigung und die <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A> -Berechtigung erforderlich.

- Beim Ausführen von WCF-Code im [Modus "Partial Trust"](../../../../docs/framework/wcf/feature-details/partial-trust.md) `public` wird `private`die Serialisierung und Deserialisierung von `readonly` Feldern (beide und ) nicht unterstützt. Das liegt daran, dass die generierte IL nicht überprüfbar ist und deshalb höhere Berechtigungen erfordert.

- Sowohl <xref:System.Runtime.Serialization.DataContractSerializer> als auch <xref:System.Xml.Serialization.XmlSerializer> werden in einer teilweise vertrauenswürdigen Umgebung unterstützt. Allerdings unterliegt die Verwendung von <xref:System.Runtime.Serialization.DataContractSerializer> den folgenden Bedingungen:

  - Alle serialisierbaren `[DataContract]` -Typen müssen öffentlich sein.

  - Alle serialisierbaren `[DataMember]` -Felder oder -Eigenschaften in einem `[DataContract]` -Typ müssen öffentlich sein und Schreib-/Lesezugriff besitzen. Die Serialisierung und Deserialisierung von `readonly` Feldern wird nicht unterstützt, wenn WCF in einer teilweise vertrauenswürdigen Anwendung ausgeführt wird.

  - Das `[Serializable]`/`ISerializable]` -Programmiermodell wird in einer teilweise vertrauenswürdigen Umgebung nicht unterstützt.

  - Bekannte Typen müssen im Code oder in einer Konfiguration auf Computerebene (`Machine.config`) angegeben werden. Bekannte Typen können aus Sicherheitsgründen nicht in einer Konfiguration auf Anwendungsebene angegeben werden.

- Typen, die <xref:System.Runtime.Serialization.IObjectReference> implementieren, lösen in einer teilweise vertrauenswürdigen Umgebung eine Ausnahme aus, weil die <xref:System.Runtime.Serialization.IObjectReference.GetRealObject%2A> -Methode die Sicherheitsberechtigung `[SecurityPermission(SecurityAction.LinkDemand, Flags=SecurityPermissionFlag.SerializationFormatter)]`erfordert.

## <a name="additional-notes-on-serialization"></a>Weitere Hinweise zur Serialisierung

Die folgenden Regeln gelten auch für vom Datenvertragsserialisierer unterstützte Typen:

- Generische Typen werden vom Datenvertragsserialisierer vollständig unterstützt.

- Nullable Wertetypen werden vom Datenvertragsserialisierungsmodul vollständig unterstützt.

- Schnittstellentypen werden entweder als <xref:System.Object> oder &#8211; im Fall von Auflistungsschnittstellen &#8211; als Auflistungstypen behandelt.

- Sowohl Strukturen als auch Klassen werden unterstützt.

- Der <xref:System.Runtime.Serialization.DataContractSerializer> unterstützt nicht das Programmiermodell, das von den <xref:System.Xml.Serialization.XmlSerializer> und ASP.NET Webdiensten verwendet wird. Es werden insbesondere keine Attribute wie <xref:System.Xml.Serialization.XmlElementAttribute> und <xref:System.Xml.Serialization.XmlAttributeAttribute>unterstützt. Um die Unterstützung für dieses Programmiermodell zu aktivieren, muss WCF so umgeschaltet werden, dass die <xref:System.Xml.Serialization.XmlSerializer> anstelle der verwendet <xref:System.Runtime.Serialization.DataContractSerializer>wird.

- Der <xref:System.DBNull> -Typ wird auf besondere Weise behandelt. Dieser Typ ist ein Singeltontyp. Bei einer Deserialisierung berücksichtigt der Deserialisierer die Singletoneinschränkung und lässt alle `DBNull` -Verweise auf die Singletoninstanz zeigen. Da `DBNull` ein serialisierbarer Typ ist, wird eine <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter%2A> -Berechtigung gefordert.

## <a name="see-also"></a>Siehe auch

- [XML- und ADO.NET-Typen in Datenverträgen](../../../../docs/framework/wcf/feature-details/xml-and-ado-net-types-in-data-contracts.md)
- [Verwenden von Datenverträgen](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
- [Serialisierbare Typen](../../../../docs/framework/wcf/feature-details/serializable-types.md)
- [Sammlungstypen in Datenverträgen](../../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md)
- [Enumerationstypen in Datenverträgen](../../../../docs/framework/wcf/feature-details/enumeration-types-in-data-contracts.md)
