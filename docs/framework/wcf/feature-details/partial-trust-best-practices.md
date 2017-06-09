---
title: "Empfehlungen f&#252;r eine teilweise vertrauensw&#252;rdige Umgebung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0d052bc0-5b98-4c50-8bb5-270cc8a8b145
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# Empfehlungen f&#252;r eine teilweise vertrauensw&#252;rdige Umgebung
In diesem Thema werden empfohlene Vorgehensweisen für die Ausführung von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in einer teilweise vertrauenswürdigen Umgebung beschrieben.  
  
## Serialisierung  
 Gehen Sie wie nachfolgend beschrieben vor, wenn Sie den <xref:System.Runtime.Serialization.DataContractSerializer> in einer teilweise vertrauenswürdigen Anwendung verwenden.  
  
-   Alle serialisierbaren Typen müssen explizit mit dem `[DataContract]`\-Attribut gekennzeichnet werden.Die folgenden Techniken werden in einer teilweise vertrauenswürdigen Umgebung nicht unterstützt:  
  
-   Das Markieren von Klassen, die serialisiert werden sollen, mit <xref:System.SerializableAttribute>  
  
-   Das Implementieren der <xref:System.Runtime.Serialization.ISerializable>\-Schnittstelle, damit eine Klasse ihren Serialisierungsprozess steuern kann  
  
### Verwenden von DataContractSerializer  
  
-   Alle mit dem `[DataContract]`\-Attribut gekennzeichneten Typen müssen öffentlich sein.Nicht öffentliche Typen können in einer teilweise vertrauenswürdigen Umgebung nicht serialisiert werden.  
  
-   Alle `[DataContract]`\-Member in einem serialisierbaren `[DataContract]`\-Typ müssen öffentlich sein.Ein Typ mit einem nicht öffentlichen `[DataMember]` kann in einer teilweise vertrauenswürdigen Umgebung nicht serialisiert werden.  
  
-   Methoden, die Serialisierungsereignisse verarbeiten \(z. B. `OnSerializing`, `OnSerialized`, `OnDeserializing` und `OnDeserialized`\), müssen als öffentlich deklariert werden.Jedoch werden sowohl explizite als auch implizite Implementierungen von <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%28System.Object%29> unterstützt.  
  
-   `[DataContract]`\-Typen, die in Assemblys implementiert und mit <xref:System.Security.AllowPartiallyTrustedCallersAttribute> gekennzeichnet sind, dürfen keine sicherheitsbezogenen Aktionen im Typenkonstruktor ausführen, da der <xref:System.Runtime.Serialization.DataContractSerializer> den Konstruktor des neu instanziierten Objekts während der Deserialisierung aufruft.Die folgenden allgemeinen Sicherheitstechniken müssen für `[DataContract]`\-Typen vermieden werden:  
  
-   Der Versuch, den teilweise vertrauenswürdigen Zugriff durch Definieren des Konstruktors für den Typ als intern oder privat zu beschränken  
  
-   Einschränken des Zugriffs auf den Typ durch Hinzufügen von `[LinkDemand]` zum Konstruktor des Typs  
  
-   Da das Objekt erfolgreich instanziiert wurde, wird davon ausgegangen, dass eventuelle vom Konstruktor erzwungene Validierungsprüfungen erfolgreich bestanden wurden.  
  
### Verwenden von IXmlSerializable  
 Die folgenden empfohlenen Vorgehensweisen gelten für Typen, die <xref:System.Xml.Serialization.IXmlSerializable> implementieren und mit <xref:System.Runtime.Serialization.DataContractSerializer> serialisiert werden:  
  
-   Die statischen <xref:System.Xml.Serialization.IXmlSerializable.GetSchema%2A>\-Methodenimplementierungen müssen `public` sein.  
  
-   Die Instanzmethoden, die die <xref:System.Xml.Serialization.IXmlSerializable>\-Schnittstelle implementieren, müssen `public` sein.  
  
## Verwenden von WCF aus vollständig vertrauenswürdigem Plattformcode, der Aufrufe teilweise vertrauenswürdiger Aufrufer zulässt  
 Das teilweise vertrauenswürdige [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] \-Sicherheitsmodell geht davon aus, dass jeder Aufrufer einer öffentlichen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Methode oder \-Eigenschaft im Codezugriffssicherheits\-Kontext \(Code Access Security, CAS\) der Hostanwendung ausgeführt wird.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] geht weiter davon aus, dass nur ein Anwendungssicherheitskontext für jede <xref:System.AppDomain> existiert und dass dieser Kontext zum Zeitpunkt der <xref:System.AppDomain>\-Erstellung durch einen vertrauenswürdigen Host eingerichtet wird \(beispielsweise durch einen Aufruf von <xref:System.AppDomain.CreateDomain%2A> oder des ASP.NET\-Anwendungs\-Managers\).  
  
 Dieses Sicherheitsmodell gilt für Anwendungen, die vom Benutzer verfasst wurden und keine zusätzlichen CAS\-Berechtigungen gewähren können, wie z. B. Benutzercode, der in einer ASP.NET\-Anwendung mittlerer Vertrauenswürdigkeit ausgeführt wird.Bei vollständig vertrauenswürdigem Plattformcode \(beispielsweise eine von Dritten erstellte Assembly, die im globalen Assemblycache installiert wird und Aufrufe von teilweise vertrauenswürdigem Code akzeptiert\) ist jedoch eine vorsichtige Vorgehensweise erforderlich, wenn [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] im Auftrag einer teilweise vertrauenswürdigen Anwendung aufgerufen wird, um das Entstehen von Sicherheitsrisiken auf Anwendungsebene zu vermeiden.  
  
 Vollständig vertrauenswürdiger Code sollte es vermeiden, den CAS\-Berechtigungsatz des aktuellen Threads zu verändern \(durch Aufrufen von <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A> oder <xref:System.Security.PermissionSet.Deny%2A>\), bevor er [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-APIs für teilweise vertrauenswürdigen Code aufruft.Das Gewähren, Abweisen oder anderweitige Erstellen von threadspezifischem Berechtigungskontext, der unabhängig vom Sicherheitskontext der Anwendungsebene ist, kann zu unerwartetem Verhalten führen.Je nach Anwendung kann dieses Verhalten zu Sicherheitslücken auf Anwendungsebene führen.  
  
 Code, der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mithilfe eines threadspezifischen Berechtigungskontexts aufruft, muss auf die Bewältigung der folgenden, möglicherweise eintretenden Situationen vorbereitet werden:  
  
-   Der threadspezifische Sicherheitskontext kann möglicherweise nicht für die Dauer des Vorgangs aufrechterhalten werden, was zu potenziellen Sicherheitsausnahmen führt.  
  
-   Interner [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Code sowie vom Benutzer bereitgestellte Rückrufe können in einem anderen Sicherheitskontext ausgeführt werden als dem, in dem der Aufruf ursprünglich initiiert wurde.Zu diesen Kontexten gehören:  
  
    -   Der Berechtigungskontext der Anwendung  
  
    -   Threadspezifischer Berechtigungskontext, der zuvor von anderen Benutzerthreads verwendet wurde, um [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] während der Lebensdauer der aktuell ausführenden <xref:System.AppDomain> aufzurufen  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stellt sicher, dass teilweise vertrauenswürdiger Code voll vertrauenswürdige Berechtigungen nur dann erhalten kann, wenn die Berechtigungen vor dem Aufrufen der öffentlichen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-APIs von einer voll vertrauenswürdigen Komponente gewährt werden.Jedoch besteht dabei nicht die Garantie, dass die Gewährung voller Vertrauenswürdigkeit auf einen bestimmten Thread, Vorgang oder eine bestimmte Benutzeraktion beschränkt ist.  
  
 Es empfiehlt sich daher, die Erstellung von threadspezifischem Berechtigungskontext durch Aufrufen von <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A> oder <xref:System.Security.PermissionSet.Deny%2A> zu vermeiden.Gewähren oder verweigern Sie stattdessen der Anwendung selbst die Berechtigung, damit <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.Deny%2A> oder <xref:System.Security.PermissionSet.PermitOnly%2A> nicht erforderlich ist.  
  
## Siehe auch  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 <xref:System.Xml.Serialization.IXmlSerializable>