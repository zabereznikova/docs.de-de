---
title: Empfehlungen für eine teilweise vertrauenswürdige Umgebung
ms.date: 03/30/2017
ms.assetid: 0d052bc0-5b98-4c50-8bb5-270cc8a8b145
ms.openlocfilehash: fca975ff4216384b970535273511eb07cd6ded68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497268"
---
# <a name="partial-trust-best-practices"></a>Empfehlungen für eine teilweise vertrauenswürdige Umgebung
Dieses Thema beschreibt bewährte Methoden bei der Ausführung von Windows Communication Foundation (WCF) in einer teilweise vertrauenswürdigen Umgebung.  
  
## <a name="serialization"></a>Serialisierung  
 Gehen Sie wie nachfolgend beschrieben vor, wenn Sie den <xref:System.Runtime.Serialization.DataContractSerializer> in einer teilweise vertrauenswürdigen Anwendung verwenden.  
  
-   Alle serialisierbaren Typen müssen explizit mit dem `[DataContract]`-Attribut gekennzeichnet werden. Die folgenden Techniken werden in einer teilweise vertrauenswürdigen Umgebung nicht unterstützt:  
  
-   Das Markieren von Klassen, die serialisiert werden sollen, mit <xref:System.SerializableAttribute>  
  
-   Das Implementieren der <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle, damit eine Klasse ihren Serialisierungsprozess steuern kann  
  
### <a name="using-datacontractserializer"></a>Verwenden von DataContractSerializer  
  
-   Alle mit dem `[DataContract]`-Attribut gekennzeichneten Typen müssen öffentlich sein. Nicht öffentliche Typen können in einer teilweise vertrauenswürdigen Umgebung nicht serialisiert werden.  
  
-   Alle `[DataContract]`-Member in einem serialisierbaren `[DataContract]`-Typ müssen öffentlich sein. Ein Typ mit einem nicht öffentlichen `[DataMember]` kann in einer teilweise vertrauenswürdigen Umgebung nicht serialisiert werden.  
  
-   Methoden, die Serialisierungsereignisse verarbeiten (z.&#160;B. `OnSerializing`, `OnSerialized`, `OnDeserializing` und `OnDeserialized`), müssen als öffentlich deklariert werden. Jedoch werden sowohl explizite als auch implizite Implementierungen von <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%28System.Object%29> unterstützt.  
  
-   `[DataContract]`-Typen, die in Assemblys implementiert und mit <xref:System.Security.AllowPartiallyTrustedCallersAttribute> gekennzeichnet sind, dürfen keine sicherheitsbezogenen Aktionen im Typenkonstruktor ausführen, da der <xref:System.Runtime.Serialization.DataContractSerializer> den Konstruktor des neu instanziierten Objekts während der Deserialisierung aufruft. Die folgenden allgemeinen Sicherheitstechniken müssen für `[DataContract]`-Typen vermieden werden:  
  
-   Der Versuch, den teilweise vertrauenswürdigen Zugriff durch Definieren des Konstruktors für den Typ als intern oder privat zu beschränken  
  
-   Einschränken des Zugriffs auf den Typ durch Hinzufügen von `[LinkDemand]` zum Konstruktor des Typs  
  
-   Da das Objekt erfolgreich instanziiert wurde, wird davon ausgegangen, dass eventuelle vom Konstruktor erzwungene Validierungsüberprüfungen erfolgreich bestanden wurden.  
  
### <a name="using-ixmlserializable"></a>Verwenden von IXmlSerializable  
 Die folgenden empfohlenen Vorgehensweisen gelten für Typen, die <xref:System.Xml.Serialization.IXmlSerializable> implementieren und mit <xref:System.Runtime.Serialization.DataContractSerializer> serialisiert werden:  
  
-   Die statischen <xref:System.Xml.Serialization.IXmlSerializable.GetSchema%2A>-Methodenimplementierungen müssen `public` sein.  
  
-   Die Instanzmethoden, die die <xref:System.Xml.Serialization.IXmlSerializable>-Schnittstelle implementieren, müssen `public` sein.  
  
## <a name="using-wcf-from-fully-trusted-platform-code-that-allows-calls-from-partially-trusted-callers"></a>Verwenden von WCF aus vollständig vertrauenswürdigem Plattformcode, der Aufrufe teilweise vertrauenswürdiger Aufrufer zulässt  
 Das Sicherheitsmodell der WCF-teilweiser Vertrauenswürdigkeit wird davon ausgegangen, dass jeder Aufrufer einer öffentlichen WCF-Methode oder Eigenschaft im Code den Zugriff (CAS) Sicherheitskontext der hostanwendung ausgeführt wird. WCF auch geht davon aus, nur ein anwendungssicherheitskontext vorhanden ist, für die einzelnen <xref:System.AppDomain>, und die diesem Kontext wird an <xref:System.AppDomain> Zeitpunkt der Erstellung von einem vertrauenswürdigen Host (z. B. durch einen Aufruf von <xref:System.AppDomain.CreateDomain%2A> oder durch des ASP.NET-Anwendungs-Managers).).  
  
 Dieses Sicherheitsmodell gilt für Anwendungen, die vom Benutzer verfasst wurden und keine zusätzlichen CAS-Berechtigungen gewähren können, wie z.&#160;B. Benutzercode, der in einer ASP.NET-Anwendung mittlerer Vertrauenswürdigkeit ausgeführt wird. Vollständig vertrauenswürdigem Plattformcode (z. B. eine Drittanbieter-Assembly, die im globalen Assemblycache installiert ist und die Aufrufe von teilweise vertrauenswürdigem Code akzeptiert) muss jedoch explizite Sorgfalt vorgehen, wenn WCF im Auftrag einer teilweise vertrauenswürdigen Anwendung aufgerufen Vermeiden Sie die Einführung von Sicherheitsrisiken auf Anwendungsebene.  
  
 Ändern des CAS-Berechtigungssatzes des aktuellen Threads ist voll vertrauenswürdigem Code vermeiden (durch Aufrufen von <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A>, oder <xref:System.Security.PermissionSet.Deny%2A>) vor dem Aufrufen von WCF-APIs im Namen von teilweise vertrauenswürdigem Code. Das Gewähren, Abweisen oder anderweitige Erstellen von threadspezifischem Berechtigungskontext, der unabhängig vom Sicherheitskontext der Anwendungsebene ist, kann zu unerwartetem Verhalten führen. Je nach Anwendung kann dieses Verhalten zu Sicherheitslücken auf Anwendungsebene führen.  
  
 Code, der Aufrufe in WCF mit einem threadspezifischer Berechtigungskontext, der darauf vorbereitet sein müssen, um den folgenden Situationen zu behandeln, die auftreten können:  
  
-   Der threadspezifische Sicherheitskontext kann möglicherweise nicht für die Dauer des Vorgangs aufrechterhalten werden, was zu potenziellen Sicherheitsausnahmen führt.  
  
-   Interne WCF-Code als auch für alle Benutzer bereitgestellte Rückrufe können in einem anderen Sicherheitskontext als dem, führen Sie unter denen der Aufruf ursprünglich initiiert wurde. Zu diesen Kontexten gehören:  
  
    -   Der Berechtigungskontext der Anwendung  
  
    -   Alle threadspezifischer Berechtigungskontext, der zuvor erstellt haben, von anderen Benutzerthreads verwendet, um in WCF während der Lebensdauer der aktuell ausführenden aufzurufen <xref:System.AppDomain>.  
  
 WCF wird sichergestellt, dass teilweise vertrauenswürdiger Code voll vertrauenswürdige Berechtigungen erhalten kann, es sei denn, diese Berechtigungen von einer voll vertrauenswürdigen Komponente vor dem Aufrufen der öffentlichen WCF-APIs übergeben werden. Jedoch besteht dabei nicht die Garantie, dass die Gewährung voller Vertrauenswürdigkeit auf einen bestimmten Thread, Vorgang oder eine bestimmte Benutzeraktion beschränkt ist.  
  
 Es empfiehlt sich daher, die Erstellung von threadspezifischem Berechtigungskontext durch Aufrufen von <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A> oder <xref:System.Security.PermissionSet.Deny%2A> zu vermeiden. Gewähren oder verweigern Sie stattdessen der Anwendung selbst die Berechtigung, damit <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.Deny%2A> oder <xref:System.Security.PermissionSet.PermitOnly%2A> nicht erforderlich ist.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.Xml.Serialization.IXmlSerializable>
