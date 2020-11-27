---
title: Serialisierbare Typen
ms.date: 03/30/2017
ms.assetid: f1c8539a-6a79-4413-b294-896f0957b2cd
ms.openlocfilehash: 4ba5fb80b3a7f4149eb49aa838826f2792147dd1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253959"
---
# <a name="serializable-types"></a>Serialisierbare Typen

Standardmäßig serialisiert der <xref:System.Runtime.Serialization.DataContractSerializer> alle öffentlich sichtbaren Typen. Alle öffentlichen Lese-/Schreibeigenschaften und Felder des Typs werden serialisiert.  
  
 Sie können das Standardverhalten ändern, indem Sie das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut und das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut auf die Typen und Member anwenden. Diese Funktion ist hilfreich in Situationen mit Typen, die nicht von Ihnen gesteuert und nicht mit weiteren Attributen versehen werden können. Der <xref:System.Runtime.Serialization.DataContractSerializer> erkennt solche nicht markierten Typen.  
  
## <a name="serialization-defaults"></a>Standardwerte für die Serialisierung  

 Sie können das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut und das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut anwenden, um die Serialisierung von Typen und Membern explizit zu steuern oder anzupassen. Darüber hinaus können Sie diese Attribute auf private Felder anwenden. Doch auch Typen, die nicht mit diesen Attributen markiert sind, werden serialisiert und deserialisiert. Folgende Regeln und Ausnahmen gelten:  
  
- Der <xref:System.Runtime.Serialization.DataContractSerializer> leitet einen Datenvertrag von Typen ohne Attribute unter Verwendung der Eigenschaften der neu erstellten Typen ab.  
  
- Alle öffentlichen Felder sowie Eigenschaften mit öffentlicher `get`- oder `set`-Methode werden serialisiert, es sei denn, Sie wenden auf diesen Member das <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>-Attribut an.  
  
- Die Serialisierungssemantik gleicht der des <xref:System.Xml.Serialization.XmlSerializer>.  
  
- In nicht markierten Typen werden nur öffentliche Typen mit Konstruktoren serialisiert, die nicht über Parameter verfügen. Die Ausnahme dieser Regel bildet das <xref:System.Runtime.Serialization.ExtensionDataObject> unter Verwendung der <xref:System.Runtime.Serialization.IExtensibleDataObject>-Schnittstelle.  
  
- Schreibgeschützte Felder, Eigenschaften ohne `get`- oder `set`-Methode sowie Eigenschaften mit interner oder privater `set`- oder `get`-Methode werden nicht serialisiert. Diese Eigenschaften werden ignoriert, und es wird keine Ausnahme ausgelöst. Ausgenommen hiervon sind get-exklusive Auflistungen.  
  
- <xref:System.Xml.Serialization.XmlSerializer>Attribute (beispielsweise `XmlElement`, `XmlAttribute`, `XmlIgnore`, `XmlInclude` usw.) werden ignoriert.  
  
- Wird das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut nicht auf einen angegebenen Typ angewendet, ignoriert der Serialisierer jeden Member des Typs, auf den das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut angewendet wurde.  
  
- Die <xref:System.Runtime.Serialization.DataContractSerializer.KnownTypes%2A>-Eigenschaft wird in Typen unterstützt, die nicht mit dem <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut markiert sind. Hierzu zählt die Unterstützung des <xref:System.Runtime.Serialization.KnownTypeAttribute>-Attributs für nicht markierte Typen.  
  
- Sollen öffentliche Member, Eigenschaften oder Felder von der Serialisierung ausgenommen werden, wenden Sie das <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>-Attribut auf den entsprechenden Member an.  
  
## <a name="inheritance"></a>Vererbung  

 Nicht markierte Typen (Typen ohne <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut) können von Typen erben, die dieses Attribut besitzen. Der umgekehrte Vorgang ist jedoch nicht möglich: Typen mit diesem Attribut können nicht von nicht markierten Typen erben. Diese Regel wird primär erzwungen, um die Abwärtskompatibilität mit Code sicherzustellen, der in früheren Versionen von .NET Framework geschrieben wurde.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Xml.Serialization.XmlSerializer>
- [Vom Datenvertragsserialisierer unterstützte Typen](types-supported-by-the-data-contract-serializer.md)
