---
title: "Persistenzdatenbankschema | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 34f69f4c-df81-4da7-b281-a525a9397a5c
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Persistenzdatenbankschema
In diesem Thema werden die vom SQL\-Workflowinstanzspeicher unterstützten öffentlichen Ansichten beschrieben.  
  
## Ansicht "Instances"  
 Die Ansicht **Instances** enthält allgemeine Informationen zu allen Workflowinstanzen in der Datenbank.  
  
|Spaltenname|Spaltentyp|Beschreibung|  
|-----------------|----------------|------------------|  
|InstanceId|UniqueIdentifier|Die ID einer Workflowinstanz.|  
|PendingTimer|DateTime|Gibt an, dass der Workflow durch eine DELAY\-Aktivität blockiert ist und nach Ablauf des Zeitgebers fortgesetzt wird.Dieser Wert ist NULL, wenn der Workflow nicht blockiert ist und auf den Ablauf eines Zeitgebers wartet.|  
|CreationTime|DateTime|Gibt an, wann der Workflow erstellt wurde.|  
|LastUpdatedTime|DateTime|Gibt an, wann der Workflow zum letzten Mal permanent in der Datenbank gespeichert wurde.|  
|ServiceDeploymentId|BigInt|Fungiert als Fremdschlüssel für die Ansicht \[ServiceDeployments\].Wenn es sich bei der aktuellen Workflowinstanz um die Instanz eines im Internet gehosteten Diensts handelt, weist diese Spalte einen Wert auf, andernfalls wird sie auf NULL festgelegt.|  
|SuspensionExceptionName|Nvarchar\(450\)|Gibt den Typ der Ausnahme an \(z. B.InvalidOperationException\), die bewirkt hat, dass der Workflow angehalten wurde.|  
|SuspensionReason|Nvarchar\(max\)|Gibt an, warum die Workflowinstanz angehalten wurde.Wenn die Instanz aufgrund einer Ausnahme angehalten wurde, enthält diese Spalte die entsprechende Meldung.<br /><br /> Wenn die Instanz manuell angehalten wurde, enthält diese Spalte den vom Benutzer angegebenen Grund für das Anhalten der Instanz.|  
|ActiveBookmarks|Nvarchar\(max\)|Wenn die Workflowinstanz im Leerlauf ist, gibt diese Eigenschaft an, bei welchen Lesezeichen die Instanz blockiert wurde.Wenn die Instanz nicht im Leerlauf ist, weist diese Spalte den Wert NULL auf.|  
|CurrentMachine|Nvarchar\(128\)|Gibt an den Namen des Computers an, auf dem die Workflowinstanz im Arbeitsspeicher geladen ist.|  
|LastMachine|Nvarchar\(450\)|Gibt den letzten Computer an, auf dem die Workflowinstanz geladen war.|  
|ExecutionStatus|Nvarchar\(450\)|Gibt den aktuellen Ausführungsstatus des Workflows an.Mögliche Status: **Wird ausgeführt**, **Leerlauf**, **Geschlossen**.|  
|IsInitialized|Bit|Gibt an, ob die Workflowinstanz initialisiert wurde.Eine initialisierte Workflowinstanz ist eine Workflowinstanz, die mindestens einmal permanent gespeichert wurde.|  
|IsSuspended|Bit|Gibt an, ob die Workflowinstanz angehalten wurde.|  
|IsCompleted|Bit|Gibt an, ob die Ausführung der Workflowinstanz beendet wurde. **Note:**  Wenn die **InstanceCompletionAction**\-Eigenschaft auf **DeleteAll** festgelegt ist, werden die Instanzen nach Beenden aus der Ansicht entfernt.|  
|EncodingOption|TinyInt|Beschreibt die Codierung, die zur Serialisierung der Dateneigenschaften verwendet wurde.<br /><br /> -   0 – Keine Codierung<br />-   1 – GzipStream|  
|ReadWritePrimitiveDataProperties|Varbinary\(max\)|Enthält serialisierte Instanzdateneigenschaften, die beim Laden der Instanz für die Workflowlaufzeit bereitgestellt werden.<br /><br /> Bei den einzelnen primitiven Eigenschaften handelt es sich um systemeigene CLR\-Typen, sodass keine speziellen Assemblys zur BLOB\-Deserialisierung benötigt werden.|  
|WriteOnlyPrimitiveDataProperties|Varbinary\(max\)|Enthält serialisierte Instanzdateneigenschaften, die beim Laden der Instanz nicht für die Workflowlaufzeit bereitgestellt werden.<br /><br /> Bei den einzelnen primitiven Eigenschaften handelt es sich um systemeigene CLR\-Typen, sodass keine speziellen Assemblys zur BLOB\-Deserialisierung benötigt werden.|  
|ReadWriteComplexDataProperties|Varbinary\(max\)|Enthält serialisierte Instanzdateneigenschaften, die beim Laden der Instanz für die Workflowlaufzeit bereitgestellt werden.<br /><br /> Für ein Deserialisierungsprogramm müssen alle in diesem BLOB gespeicherten Objekttypen bekannt sein.|  
|WriteOnlyComplexDataProperties|Varbinary\(max\)|Enthält serialisierte Instanzdateneigenschaften, die beim Laden der Instanz nicht für die Workflowlaufzeit bereitgestellt werden.<br /><br /> Für ein Deserialisierungsprogramm müssen alle in diesem BLOB gespeicherten Objekttypen bekannt sein.|  
|IdentityName|Nvarchar\(max\)|Der Name der Workflowdefinition.|  
|IdentityPackage|Nvarchar\(max\)|Die Paketinformationen, die beim Erstellen des Workflows angegeben wurden \(z. B. der Assemblyname\).|  
|Build|BigInt|Die Buildnummer der Workflowversion.|  
|Major|BigInt|Die Hauptversionsnummer der Workflowversion.|  
|Minor|BigInt|Die Nebenversionsnummer der Workflowversion.|  
|Revision|BigInt|Die Revisionsnummer der Workflowversion.|  
  
> [!CAUTION]
>  Die Ansicht **Instances** enthält auch einen DELETE\-Trigger.Benutzer mit den entsprechenden Berechtigungen können in dieser Ansicht Löschanweisungen ausführen, mit denen die Entfernung von Workflowinstanzen aus der Datenbank erzwungen wird.Das Löschen direkt über die Ansicht wird jedoch nur empfohlen, wenn keine andere Möglichkeit besteht, da unter der Workflowlaufzeit initialisierte Löschvorgänge zu unbeabsichtigten Ergebnissen führen können.Verwenden Sie stattdessen den Verwaltungsendpunkt der Workflowinstanz, um die Instanz über die Workflowlaufzeit zu beenden.Wenn Sie eine große Anzahl von Instanzen in der Ansicht löschen möchten, stellen Sie sicher, dass keine aktiven Laufzeiten Vorgänge für diese Instanzen ausführen.  
  
## Ansicht "ServiceDeployments"  
 Die Ansicht **ServiceDeployments** enthält Bereitstellungsinformationen für alle im Internet \(IIS\/WAS\) gehosteten Workflowdienste.Jede im Internet gehostete Workflowinstanz weist ein **ServiceDeploymentId**\-Element auf, das auf eine Zeile in dieser Ansicht verweist.  
  
|Spaltenname|Spaltentyp|Beschreibung|  
|-----------------|----------------|------------------|  
|ServiceDeploymentId|BigInt|Der Primärschlüssel für diese Ansicht.|  
|SiteName|Nvarchar\(max\)|Stellt den Namen der Website dar, die für den Workflowdienst enthält \(z. B.**Standardwebsite**\).|  
|RelativeServicePath|Nvarchar\(max\)|Stellt den virtuellen Pfad relativ zur Website dar, die auf den Workflowdienst verweist.\(z. B.**\/app1\/PurchaseOrderService.svc**\).|  
|RelativeApplicationPath|Nvarchar\(max\)|Stellt den virtuellen Pfad relativ zur Website dar, die auf eine Anwendung verweist, die den Workflowdienst enthält.\(z. B.**\/app1**\).|  
|ServiceName|Nvarchar\(max\)|Der Name des Workflowdiensts.\(z. B.**PurchaseOrderService**\).|  
|ServiceNamespace|Nvarchar\(max\)|Der Namespace des Workflowdiensts.\(z. B.**MyCompany**\).|  
  
 Die Ansicht "ServiceDeployments" enthält ebenfalls einen DELETE\-Trigger.Benutzer mit den entsprechenden Berechtigungen können in dieser Ansicht Löschanweisungen ausführen, mit denen ServiceDeployment\-Einträge aus der Datenbank entfernt werden.Hinweis:  
  
1.  Das Löschen von Einträgen in dieser Ansicht ist aufwändig, da die gesamte Datenbank vor der Ausführung dieses Vorgangs gesperrt werden muss.Dies ist notwendig, um zu vermeiden, dass eine Workflowinstanz auf einen nicht vorhandenen ServiceDeployment\-Eintrag verweist.Führen Sie Löschvorgänge in dieser Ansicht nur durch, wenn die Datenbank nicht in Betrieb ist bzw. innerhalb von Wartungszeitfenstern.  
  
2.  Bei dem Versuch, eine ServiceDeployment\-Zeile zu löschen, auf die Einträge in der Ansicht **Instances** verweisen, wird keine Aktion ausgeführt.Es können nur ServiceDeployment\-Zeilen mit 0 \(null\) Verweisen gelöscht werden.  
  
## Ansicht "InstancePromotedProperties"  
 Die Ansicht **InstancePromotedProperties** enthält Informationen für alle vom Benutzer angegebenen höher gestuften Eigenschaften.Eine höher gestufte Eigenschaft fungiert als Eigenschaft erster Klasse, die vom Benutzer in Abfragen zum Abrufen von Instanzen verwendet werden kann.Ein Benutzer kann beispielsweise eine Höherstufung für die PurchaseOrder\-Eigenschaft hinzufügen, die den Betrag einer Bestellung in der Spalte **Value1** speichert.Auf diese Weise können Sie eine Abfrage ausführen, die alle Bestellungen zurückgibt, deren Betrag einen bestimmten Wert überschreitet.  
  
||||  
|-|-|-|  
|Spaltenname|Spaltentyp|Beschreibung|  
|InstanceId|UniqueIdentifier|Die ID der Workflowinstanz.|  
|EncodingOption|TinyInt|Beschreibt die Codierung, die zur Serialisierung der höher gestuften binären Eigenschaften verwendet wurde.<br /><br /> -   0 – Keine Codierung<br />-   1 – GZipStream|  
|PromotionName|Nvarchar\(400\)|Der Name der dieser Instanz zugeordneten Höherstufung.Dieser Name wird benötigt, um den generischen Spalten in dieser Zeile Kontext hinzuzufügen.<br /><br /> Mit dem PromotionName\-Wert von PurchaseOrder kann beispielsweise angegeben werden, dass Value1 den Betrag der Bestellung, Value2 den Namen des Kunden, der die Bestellung aufgegeben hat, Value3 die Adresse des Kunden enthält usw.|  
|Value\[1\-32\]|SqlVariant|Value\[1\-32\] enthält Werte, die in einer SqlVariant\-Spalte gespeichert werden können.Eine Heraufstufung darf maximal 32 SqlVariant\-Werte enthalten.|  
|Value\[33\-64\]|Varbinary\(max\)|Value\[33\-64\] enthält serialisierte Werte. Value33 kann beispielsweise ein JPEG\-Bild eines gekauften Artikels enthalten.Eine Heraufstufung darf maximal 32 binäre Eigenschaften enthalten.|  
  
 Die Ansicht "InstancePromotedProperties" ist schemagebunden. Das heißt, dass Benutzer Indizes für eine oder mehrere Spalten hinzufügen können, um Abfragen in dieser Ansicht zu optimieren.  
  
> [!NOTE]
>  Eine indizierte Ansicht erfordert mehr Speicherplatz und Mehraufwand bei der Verarbeitung.Weitere Informationen finden Sie unter [Improving Performance with SQL Server 2008 Indexed Views](http://go.microsoft.com/fwlink/?LinkId=179529).