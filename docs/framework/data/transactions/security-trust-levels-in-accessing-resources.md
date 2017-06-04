---
title: "Vertrauensebenen f&#252;r Sicherheit beim Zugriff auf Ressourcen  | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fb5be924-317d-4d69-b33a-3d18ecfb9d6e
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Vertrauensebenen f&#252;r Sicherheit beim Zugriff auf Ressourcen 
In diesem Thema wird erläutert, wie der Zugriff auf die Typen von Ressourcen eingeschränkt wird, die <xref:System.Transactions> verfügbar macht.  
  
 Es gibt drei Hauptvertrauensebenen für <xref:System.Transactions>.Die Vertrauensebenen werden basierend auf den Ressourcentypen definiert, die <xref:System.Transactions> verfügbar macht, und auf der Grundlage der Vertrauensebene, die für den Zugriff auf diese Ressourcen erforderlich sein soll.Die Ressourcen, auf die <xref:System.Transactions> Zugriff gewährt, sind Systemspeicher, freigegebene prozessübergreifende Ressourcen und systemweite Ressourcen.Die Ebenen sind:  
  
-   **AllowPartiallyTrustedCallers** \(APTCA\) für Anwendungen, die Transaktionen innerhalb einer einzelnen Anwendungsdomäne verwenden  
  
-   **DistributedTransactionPermission** \(DTP\) für Anwendungen, die verteilte Transaktionen verwenden  
  
-   Volle Vertrauenswürdigkeit für dauerhafte Ressourcen, Konfigurationsverwaltungsanwendungen und Legacy\-Interop\-Anwendungen  
  
> [!NOTE]
>  Sie sollten keine Eintragungsschnittstelle mit Identitätswechselkontexten aufrufen.  
  
## Vertrauensebenen  
  
### APTCA \(teilweise vertrauenswürdig\)  
 Die <xref:System.Transactions>\-Assembly kann von teilweise vertrauenswürdigem Code aufgerufen werden, da sie mit dem **AllowPartiallyTrustedCallers**\-Attribut \(APTCA\) markiert ist.Dieses Attribut entfernt im Wesentlichen die implizite <xref:System.Security.Permissions.SecurityAction> für den **FullTrust**\-Berechtigungssatz, die andernfalls für jede öffentlich zugängliche Methode jeden Typs eingerichtet ist.Für einige Typen und Member sind allerdings weiterhin stärkere Berechtigungen erforderlich.  
  
 Das APTCA\-Attribut ermöglicht es Anwendungen, Transaktionen in teilweiser Vertrauenswürdigkeit innerhalb einer einzelnen Anwendungsdomäne zu verwenden.Dadurch ist die Verwendung nicht eskalierter Transaktionen und flüchtiger Eintragungen möglich, die zur Fehlerbehandlung verwendet werden können.Ein Beispiel dafür sind eine Transaktions\-Hashtabelle und eine Anwendung, die sie verwendet.Daten können mit einer einzigen Transaktion der Hashtabelle hinzugefügt oder aus ihr entfernt werden.Wird später ein Rollback für diese Transaktion ausgeführt, können alle Änderungen, die im Rahmen dieser Transaktion an der Hashtabelle vorgenommen wurden, wieder rückgängig gemacht werden.  
  
### DistributedTransactionPermission \(DTP\)  
 Wenn eine <xref:System.Transactions>\-Transaktion zur Verwaltung durch MSDTC eskaliert wird, fordert <xref:System.Transactions> die <xref:System.Transactions.DistributedTransactionPermission> \(DTP\) auf, die verteilte Transaktion zu erstellen.Das bedeutet, dass dem Code, der für die Eskalation der Transaktion verantwortlich ist \(beispielsweise durch Serialisierung oder zusätzliche dauerhafte Eintragungen\), DTP erteilt werden muss.Der Code, der ursprünglich die <xref:System.Transactions>\-Transaktion erstellt hat, muss diese Berechtigung nicht unbedingt besitzen.  
  
### FullTrust\-Linkaufrufe  
 Diese Berechtigungsstufe ist dazu gedacht, die Anwendungen zu beschränken, die in dauerhafte Ressourcen schreiben.Bei einem Fehler muss die Anwendung in der Lage sein, die Verbindung zum Transaktions\-Manager wiederherzustellen, um das Endergebnis der Transaktion in Erfahrung zu bringen und dauerhafte Daten aktualisieren zu können.Dieser Anwendungstyp wird als dauerhafter Quellen\-Manager bezeichnet.Ein klassisches Beispiel für diesen Anwendungstyp ist SQL.  
  
 Um die Wiederherstellung zu ermöglichen, ist dieser Anwendungstyp in der Lage, Systemressourcen permanent zu belegen.Das liegt daran, dass sich der wiederherstellungsfähige Transaktions\-Manager Transaktionen, für die ein Commit ausgeführt wurde, so lange merken muss, bis er bestätigen kann, dass alle Ressourcen\-Manager, die an der Transaktion teilnehmen, Kenntnis über das Ergebnis erhalten haben.Daher benötigt dieser Anwendungstyp volle Vertrauenswürdigkeit und sollte erst nach Erteilung dieser Vertrauensebene ausgeführt werden.  
  
 Weitere Informationen zu permanenten Eintragungen und zur Wiederherstellung finden Sie in den Themen [Eintragen von Ressourcen als Teilnehmer an einer Transaktion ](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md) und [Durchführen einer Wiederherstellung ](../../../../docs/framework/data/transactions/performing-recovery.md).  
  
 Anwendungen, die Legacy\-Interop\-Aufgaben mit COM\+ ausführen, benötigen ebenfalls die volle Vertrauenswürdigkeit.  
  
 Es folgt eine Liste von Typen und Membern, die nicht von teilweise vertrauenswürdigem Code aufgerufen werden können, da sie mit dem deklarativen Sicherheitsattribut **FullTrust** ausgestattet sind:  
  
 `PermissionSetAttribute(SecurityAction.LinkDemand, Name := "FullTrust")`  
  
-   <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=fullName>  
  
-   <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A>  
  
-   <xref:System.Transactions.TransactionInterop>  
  
-   <xref:System.Transactions.TransactionManager.DistributedTransactionStarted>  
  
-   <xref:System.Transactions.HostCurrentTransactionCallback>  
  
-   <xref:System.Transactions.TransactionManager.Reenlist%2A>  
  
-   <xref:System.Transactions.TransactionManager.RecoveryComplete%2A>  
  
-   <xref:System.Transactions.TransactionScope.%23ctor%28System.Transactions.TransactionScopeOption%2CSystem.Transactions.TransactionOptions%2CSystem.Transactions.EnterpriseServicesInteropOption%29>  
  
 Lediglich der direkte Aufrufer muss über den **FullTrust**\-Berechtigungssatz verfügen, um die weiter oben aufgeführten Typen und Methoden zu verwenden.