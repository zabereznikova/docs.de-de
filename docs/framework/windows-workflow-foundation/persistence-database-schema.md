---
title: Persistenzdatenbankschema
ms.date: 03/30/2017
ms.assetid: 34f69f4c-df81-4da7-b281-a525a9397a5c
ms.openlocfilehash: 04b57789e7c1ab6bfebd9c9b345ee0fb7dfb3e66
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558237"
---
# <a name="persistence-database-schema"></a>Persistenzdatenbankschema
In diesem Thema werden die vom SQL-Workflowinstanzspeicher unterstützten öffentlichen Ansichten beschrieben.  
  
## <a name="instances-view"></a>Ansicht "Instanzen"  
 Die **Instanzen** Ansicht enthält allgemeine Informationen zu allen Workflow Instanzen in der Datenbank.  
  
|Spaltenname|Spaltentyp|BESCHREIBUNG|  
|-----------------|-----------------|-----------------|  
|InstanceId|UniqueIdentifier|Die ID einer Workflowinstanz.|  
|PendingTimer|Datetime|Gibt an, dass der Workflow durch eine DELAY-Aktivität blockiert ist und nach Ablauf des Zeitgebers fortgesetzt wird. Dieser Wert ist NULL, wenn der Workflow nicht blockiert ist und auf den Ablauf eines Zeitgebers wartet.|  
|CreationTime|Datetime|Gibt an, wann der Workflow erstellt wurde.|  
|LastUpdatedTime|Datetime|Gibt an, wann der Workflow zum letzten Mal permanent in der Datenbank gespeichert wurde.|  
|ServiceDeploymentId|BigInt|Fungiert als Fremdschlüssel für die Ansicht [ServiceDeployments]. Wenn es sich bei der aktuellen Workflowinstanz um die Instanz eines im Internet gehosteten Diensts handelt, weist diese Spalte einen Wert auf, andernfalls wird sie auf NULL festgelegt.|  
|SuspensionExceptionName|Nvarchar(450)|Gibt den Typ der Ausnahme (z. B. InvalidOperationException) an, die das Anhalten des Workflows verursacht hat.|  
|SuspensionReason|Nvarchar(max)|Gibt an, warum die Workflowinstanz angehalten wurde. Wenn die Instanz aufgrund einer Ausnahme angehalten wurde, enthält diese Spalte die entsprechende Meldung.<br /><br /> Wenn die Instanz manuell angehalten wurde, enthält diese Spalte den vom Benutzer angegebenen Grund für das Anhalten der Instanz.|  
|ActiveBookmarks|Nvarchar(max)|Wenn die Workflowinstanz im Leerlauf ist, gibt diese Eigenschaft an, bei welchen Lesezeichen die Instanz blockiert wurde. Wenn die Instanz nicht im Leerlauf ist, weist diese Spalte den Wert NULL auf.|  
|CurrentMachine|Nvarchar(128)|Gibt den Namen des Computers an, auf dem die Workflowinstanz im Arbeitsspeicher geladen ist.|  
|LastMachine|Nvarchar(450)|Gibt den letzten Computer an, auf dem die Workflowinstanz geladen war.|  
|ExecutionStatus|Nvarchar(450)|Gibt den aktuellen Ausführungsstatus des Workflows an. Zu den möglichen Zuständen gehören das **Ausführen**, das **Leerlauf**, das **geschlossene**.|  
|IsInitialized|bit|Gibt an, ob die Workflowinstanz initialisiert wurde. Eine initialisierte Workflowinstanz ist eine Workflowinstanz, die mindestens einmal permanent gespeichert wurde.|  
|IsSuspended|bit|Gibt an, ob die Workflowinstanz angehalten wurde.|  
|IsCompleted|bit|Gibt an, ob die Ausführung der Workflowinstanz beendet wurde. **Hinweis:**  IWenn die **InstanceCompletionAction** -Eigenschaft auf **DeleteAll**festgelegt ist, werden die Instanzen nach dem Abschluss aus der Ansicht entfernt.|  
|EncodingOption|TinyInt|Beschreibt die Codierung, die zur Serialisierung der Dateneigenschaften verwendet wurde.<br /><br /> -0 – keine Codierung<br />-1 – GZipStream|  
|ReadWritePrimitiveDataProperties|Varbinary(max)|Enthält serialisierte Instanzdateneigenschaften, die beim Laden der Instanz für die Workflowlaufzeit bereitgestellt werden.<br /><br /> Bei den einzelnen primitiven Eigenschaften handelt es sich um systemeigene CLR-Typen, sodass keine speziellen Assemblys zur BLOB-Deserialisierung benötigt werden.|  
|WriteOnlyPrimitiveDataProperties|Varbinary(max)|Enthält serialisierte Instanzdateneigenschaften, die beim Laden der Instanz nicht für die Workflowlaufzeit bereitgestellt werden.<br /><br /> Bei den einzelnen primitiven Eigenschaften handelt es sich um systemeigene CLR-Typen, sodass keine speziellen Assemblys zur BLOB-Deserialisierung benötigt werden.|  
|ReadWriteComplexDataProperties|Varbinary(max)|Enthält serialisierte Instanzdateneigenschaften, die beim Laden der Instanz für die Workflowlaufzeit bereitgestellt werden.<br /><br /> Für ein Deserialisierungsprogramm müssen alle in diesem BLOB gespeicherten Objekttypen bekannt sein.|  
|WriteOnlyComplexDataProperties|Varbinary(max)|Enthält serialisierte Instanzdateneigenschaften, die beim Laden der Instanz nicht für die Workflowlaufzeit bereitgestellt werden.<br /><br /> Für ein Deserialisierungsprogramm müssen alle in diesem BLOB gespeicherten Objekttypen bekannt sein.|  
|IdentityName|Nvarchar(max)|Der Name der Workflowdefinition.|  
|IdentityPackage|Nvarchar(max)|Die Paketinformationen, die beim Erstellen des Workflows angegeben wurden (z. B. der Assemblyname).|  
|Build|BigInt|Die Buildnummer der Workflowversion.|  
|Hauptversion|BigInt|Die Hauptversionsnummer der Workflowversion.|  
|Gering|BigInt|Die Nebenversionsnummer der Workflowversion.|  
|Revision|BigInt|Die Revisionsnummer der Workflowversion.|  
  
> [!CAUTION]
> Die **Instanzen** Ansicht enthält auch einen DELETE-Vorgang. Benutzer mit den entsprechenden Berechtigungen können in dieser Ansicht Löschanweisungen ausführen, mit denen die Entfernung von Workflowinstanzen aus der Datenbank erzwungen wird. Das Löschen direkt über die Ansicht wird jedoch nur empfohlen, wenn keine andere Möglichkeit besteht, da unter der Workflowlaufzeit initialisierte Löschvorgänge zu unbeabsichtigten Ergebnissen führen können. Verwenden Sie stattdessen den Verwaltungsendpunkt der Workflowinstanz, um die Instanz über die Workflowlaufzeit zu beenden. Wenn Sie eine große Anzahl von Instanzen in der Ansicht löschen möchten, stellen Sie sicher, dass keine aktiven Laufzeiten Vorgänge für diese Instanzen ausführen.  
  
## <a name="servicedeployments-view"></a>Ansicht "ServiceDeployments"  
 Die Ansicht " **servicedeployments** " enthält Bereitstellungs Informationen für alle von Web (IIS/was) gehosteten Workflow Dienste. Jede Workflow Instanz, die im Internet gehostet wird, enthält eine **servicedeploymentid** , die auf eine Zeile in dieser Sicht verweist.  
  
|Spaltenname|Spaltentyp|BESCHREIBUNG|  
|-----------------|-----------------|-----------------|  
|ServiceDeploymentId|BigInt|Der Primärschlüssel für diese Ansicht.|  
|SiteName|Nvarchar(max)|Stellt den Namen der Site dar, die den Workflow Dienst enthält (z. b. **Standard Website**).|  
|RelativeServicePath|Nvarchar(max)|Stellt den virtuellen Pfad relativ zur Website dar, die auf den Workflowdienst verweist. Beispiels.  **/App1/PurchaseOrderService.svc**).|  
|RelativeApplicationPath|Nvarchar(max)|Stellt den virtuellen Pfad relativ zur Website dar, die auf eine Anwendung verweist, die den Workflowdienst enthält. (z. b. **/App1**).|  
|Dienstname|Nvarchar(max)|Der Name des Workflowdiensts. (z. b. **purchaseorderservice**).|  
|ServiceNamespace|Nvarchar(max)|Der Namespace des Workflowdiensts. (z. b. **MyCompany**).|  
  
 Die Ansicht "ServiceDeployments" enthält ebenfalls einen DELETE-Trigger. Benutzer mit den entsprechenden Berechtigungen können in dieser Ansicht Löschanweisungen ausführen, mit denen ServiceDeployment-Einträge aus der Datenbank entfernt werden. Beachten Sie dabei Folgendes:  
  
1. Das Löschen von Einträgen in dieser Ansicht ist aufwändig, da die gesamte Datenbank vor der Ausführung dieses Vorgangs gesperrt werden muss. Dies ist notwendig, um zu vermeiden, dass eine Workflowinstanz auf einen nicht vorhandenen ServiceDeployment-Eintrag verweist. Führen Sie Löschvorgänge in dieser Ansicht nur durch, wenn die Datenbank nicht in Betrieb ist bzw. innerhalb von Wartungszeitfenstern.  
  
2. Jeder Versuch, eine Zeile für die Dienst Bereitstellung zu löschen, auf die durch Einträge in der **Instanzen** Ansicht verwiesen wird, führt zu einem No-op-Vorgang. Es können nur ServiceDeployment-Zeilen mit 0 (null) Verweisen gelöscht werden.  
  
## <a name="instancepromotedproperties-view"></a>Ansicht "InstancePromotedProperties"  
 Die **instancepromotedproperties** -Sicht enthält Informationen für alle höher gestuften Eigenschaften, die vom Benutzer angegeben werden. Eine höher gestufte Eigenschaft fungiert als Eigenschaft erster Klasse, die vom Benutzer in Abfragen zum Abrufen von Instanzen verwendet werden kann.  Ein Benutzer könnte z. b. eine PurchaseOrder-herauf Stufung hinzufügen, die immer die Kosten eines Auftrags in der **value1** -Spalte speichert. Auf diese Weise können Sie eine Abfrage ausführen, die alle Bestellungen zurückgibt, deren Betrag einen bestimmten Wert überschreitet.  
  
|Spaltentyp|Spaltentyp|BESCHREIBUNG|  
|-|-|-|  
|InstanceId|UniqueIdentifier|Die ID der Workflowinstanz.|  
|EncodingOption|TinyInt|Beschreibt die Codierung, die zur Serialisierung der höher gestuften binären Eigenschaften verwendet wurde.<br /><br /> -0 – keine Codierung<br />-1 – GZipStream|  
|PromotionName|Nvarchar(400)|Der Name der dieser Instanz zugeordneten Höherstufung. Dieser Name wird benötigt, um den generischen Spalten in dieser Zeile Kontext hinzuzufügen.<br /><br /> Mit dem PromotionName-Wert von PurchaseOrder kann beispielsweise angegeben werden, dass Value1 den Betrag der Bestellung, Value2 den Namen des Kunden, der die Bestellung aufgegeben hat, Value3 die Adresse des Kunden enthält usw.|  
|Value[1-32]|SqlVariant|Value[1-32] enthält Werte, die in einer SqlVariant-Spalte gespeichert werden können. Eine Heraufstufung darf maximal 32 SqlVariant-Werte enthalten.|  
|Value[33-64]|Varbinary(max)|Value[33-64] enthält serialisierte Werte. Value33 kann beispielsweise ein JPEG-Bild eines gekauften Artikels enthalten. Eine Heraufstufung darf maximal 32 binäre Eigenschaften enthalten.|  
  
 Die Ansicht "InstancePromotedProperties" ist schemagebunden. Das heißt, dass Benutzer Indizes für eine oder mehrere Spalten hinzufügen können, um Abfragen in dieser Ansicht zu optimieren.  
  
> [!NOTE]
> Eine indizierte Ansicht erfordert mehr Speicherplatz und zusätzlichen Verarbeitungsaufwand. Weitere Informationen finden Sie unter [verbessern der Leistung mit SQL Server 2008-indizierten Sichten](/previous-versions/sql/sql-server-2008/dd171921(v=sql.100)) .
