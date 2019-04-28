---
title: Empfehlungen für eine teilweise vertrauenswürdige Umgebung
ms.date: 03/30/2017
ms.assetid: 0d052bc0-5b98-4c50-8bb5-270cc8a8b145
ms.openlocfilehash: c83c36020cfd5b41e99ff9eeb7968d0b5df909a6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769459"
---
# <a name="partial-trust-best-practices"></a>Empfehlungen für eine teilweise vertrauenswürdige Umgebung
Dieses Thema beschreibt bewährte Methoden bei der Ausführung von Windows Communication Foundation (WCF) in einer teilweise vertrauenswürdigen Umgebung.  
  
## <a name="serialization"></a>Serialisierung  
 Gehen Sie wie nachfolgend beschrieben vor, wenn Sie den <xref:System.Runtime.Serialization.DataContractSerializer> in einer teilweise vertrauenswürdigen Anwendung verwenden.  
  
- Alle serialisierbaren Typen müssen explizit mit dem `[DataContract]`-Attribut gekennzeichnet werden. Die folgenden Techniken werden in einer teilweise vertrauenswürdigen Umgebung nicht unterstützt:  
  
- Das Markieren von Klassen, die serialisiert werden sollen, mit <xref:System.SerializableAttribute>  
  
- Das Implementieren der <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle, damit eine Klasse ihren Serialisierungsprozess steuern kann  
  
### <a name="using-datacontractserializer"></a>Verwenden von DataContractSerializer  
  
- Alle mit dem `[DataContract]`-Attribut gekennzeichneten Typen müssen öffentlich sein. Nicht öffentliche Typen können in einer teilweise vertrauenswürdigen Umgebung nicht serialisiert werden.  
  
- Alle `[DataContract]`-Member in einem serialisierbaren `[DataContract]`-Typ müssen öffentlich sein. Ein Typ mit einem nicht öffentlichen `[DataMember]` kann in einer teilweise vertrauenswürdigen Umgebung nicht serialisiert werden.  
  
- Methoden, die Serialisierungsereignisse verarbeiten (z.&amp;#160;B. `OnSerializing`, `OnSerialized`, `OnDeserializing` und `OnDeserialized`), müssen als öffentlich deklariert werden. Jedoch werden sowohl explizite als auch implizite Implementierungen von <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%28System.Object%29> unterstützt.  
  
- `[DataContract]`-Typen, die in Assemblys implementiert und mit <xref:System.Security.AllowPartiallyTrustedCallersAttribute> gekennzeichnet sind, dürfen keine sicherheitsbezogenen Aktionen im Typenkonstruktor ausführen, da der <xref:System.Runtime.Serialization.DataContractSerializer> den Konstruktor des neu instanziierten Objekts während der Deserialisierung aufruft. Die folgenden allgemeinen Sicherheitstechniken müssen für `[DataContract]`-Typen vermieden werden:  
  
- Der Versuch, den teilweise vertrauenswürdigen Zugriff durch Definieren des Konstruktors für den Typ als intern oder privat zu beschränken  
  
- Einschränken des Zugriffs auf den Typ durch Hinzufügen von `[LinkDemand]` zum Konstruktor des Typs  
  
- Da das Objekt erfolgreich instanziiert wurde, wird davon ausgegangen, dass eventuelle vom Konstruktor erzwungene Validierungsprüfungen erfolgreich bestanden wurden.  
  
### <a name="using-ixmlserializable"></a>Verwenden von IXmlSerializable  
 Die folgenden empfohlenen Vorgehensweisen gelten für Typen, die <xref:System.Xml.Serialization.IXmlSerializable> implementieren und mit <xref:System.Runtime.Serialization.DataContractSerializer> serialisiert werden:  
  
- Die statischen <xref:System.Xml.Serialization.IXmlSerializable.GetSchema%2A>-Methodenimplementierungen müssen `public` sein.  
  
- Die Instanzmethoden, die die <xref:System.Xml.Serialization.IXmlSerializable>-Schnittstelle implementieren, müssen `public` sein.  
  
## <a name="using-wcf-from-fully-trusted-platform-code-that-allows-calls-from-partially-trusted-callers"></a>Verwenden von WCF aus vollständig vertrauenswürdigem Plattformcode, der Aufrufe teilweise vertrauenswürdiger Aufrufer zulässt  
 Das Sicherheitsmodell der WCF-teilweiser Vertrauenswürdigkeit wird davon ausgegangen, dass jeder Aufrufer einer öffentlichen WCF-Methode oder Eigenschaft im Kontext Code Access Security (CAS) der hostanwendung ausgeführt wird. WCF auch geht davon aus, nur ein anwendungssicherheitskontext für jede vorhanden <xref:System.AppDomain>, und die diesem Kontext wird an <xref:System.AppDomain> Zeitpunkt der Erstellung von einem vertrauenswürdigen Host (z. B. durch einen Aufruf von <xref:System.AppDomain.CreateDomain%2A> oder durch des ASP.NET-Anwendungs-Managers).).  
  
 Dieses Sicherheitsmodell gilt für Anwendungen, die vom Benutzer verfasst wurden und keine zusätzlichen CAS-Berechtigungen gewähren können, wie z.&amp;#160;B. Benutzercode, der in einer ASP.NET-Anwendung mittlerer Vertrauenswürdigkeit ausgeführt wird. Vollständig vertrauenswürdigem Plattformcode (beispielsweise eine Drittanbieter-Assembly, die im globalen Assemblycache installiert ist und akzeptiert Aufrufe von teilweise vertrauenswürdigem Code) muss jedoch explizit Sorgfalt walten lassen beim Aufrufen von in WCF im Auftrag einer teilweise vertrauenswürdigen Anwendung Vermeiden Sie das Einführen von Sicherheitsrisiken auf Anwendungsebene.  
  
 Voll vertrauenswürdigem Code vermeiden, ändern den CAS-Berechtigungssatz, der den aktuellen Thread (durch Aufrufen von <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A>, oder <xref:System.Security.PermissionSet.Deny%2A>) vor dem Aufrufen von WCF-APIs im Namen von teilweise vertrauenswürdigem Code. Das Gewähren, Abweisen oder anderweitige Erstellen von threadspezifischem Berechtigungskontext, der unabhängig vom Sicherheitskontext der Anwendungsebene ist, kann zu unerwartetem Verhalten führen. Je nach Anwendung kann dieses Verhalten zu Sicherheitslücken auf Anwendungsebene führen.  
  
 Code, der Aufrufe in WCF über eine threadspezifischer Berechtigungskontext darauf vorbereitet sein müssen, um den folgenden Situationen zu behandeln, die auftreten können:  
  
- Der threadspezifische Sicherheitskontext kann möglicherweise nicht für die Dauer des Vorgangs aufrechterhalten werden, was zu potenziellen Sicherheitsausnahmen führt.  
  
- Interne WCF-Code als auch für alle Benutzer bereitgestellte Rückrufe können in einem anderen Sicherheitskontext als dem Ausführen unter denen der Aufruf ursprünglich initiiert wurde. Zu diesen Kontexten gehören:  
  
    - Der Berechtigungskontext der Anwendung  
  
    - Alle threadspezifischer Berechtigungskontext, der zuvor erstellt haben, von anderen Benutzerthreads verwendet, um in WCF während der Lebensdauer der aktuell ausführenden aufzurufen <xref:System.AppDomain>.  
  
 WCF wird sichergestellt, dass teilweise vertrauenswürdiger Code voll vertrauenswürdige Berechtigungen abrufen kann, es sei denn, diese Berechtigungen von einer voll vertrauenswürdigen Komponente vor dem Aufruf der öffentlichen WCF-APIs übergeben werden. Jedoch besteht dabei nicht die Garantie, dass die Gewährung voller Vertrauenswürdigkeit auf einen bestimmten Thread, Vorgang oder eine bestimmte Benutzeraktion beschränkt ist.  
  
 Es empfiehlt sich daher, die Erstellung von threadspezifischem Berechtigungskontext durch Aufrufen von <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A> oder <xref:System.Security.PermissionSet.Deny%2A> zu vermeiden. Gewähren oder verweigern Sie stattdessen der Anwendung selbst die Berechtigung, damit <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.Deny%2A> oder <xref:System.Security.PermissionSet.PermitOnly%2A> nicht erforderlich ist.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Xml.Serialization.IXmlSerializable>
