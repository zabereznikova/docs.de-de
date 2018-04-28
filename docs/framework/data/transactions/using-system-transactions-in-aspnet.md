---
title: Verwenden von System.Transactions in ASP.NET
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1c20905c8eafb1ac31702a46878e517ac090e484
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="using-systemtransactions-in-aspnet"></a>Verwenden von System.Transactions in ASP.NET
In diesem Thema wird beschrieben, wie Sie <xref:System.Transactions> erfolgreich in einer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendung verwenden können.  
  
## <a name="enable-distributedtransactionpermission-in-aspnet"></a>Aktivieren von DistributedTransactionPermission in ASP.NET  
 <xref:System.Transactions> unterstützt teilweise vertrauenswürdige Aufrufer und wird mit dem **AllowPartiallyTrustedCallers** -Attribut (APTCA) markiert. Die Vertrauensebenen für <xref:System.Transactions> werden auf der Basis der Ressourcentypen (beispielsweise Systemspeicher, freigegebene prozessübergreifende Ressourcen, systemweite Ressourcen und andere Ressourcen) definiert, die <xref:System.Transactions> verfügbar macht, und auf der Basis der Vertrauensebene, die erforderlich sein soll, um auf diese Ressourcen zuzugreifen. In einer teilweise vertrauenswürdigen Umgebung kann eine nicht vollständig vertrauenswürdige Assembly Transaktionen nur innerhalb der Anwendungsdomäne nutzen (in diesem Fall ist die einzige geschützte Ressource der Systemspeicher), sofern ihr nicht die <xref:System.Transactions.DistributedTransactionPermission>erteilt wird.  
  
 <xref:System.Transactions.DistributedTransactionPermission> wird immer dann gefordert, wenn die Transaktionsverwaltung eskaliert wird, um vom Microsoft Distributed Transaction Coordinator (MSDTC) verwaltet zu werden. Diese Art des Szenarios verwendet prozessübergreifende Ressourcen und insbesondere eine globale Ressource, bei der es sich um den reservierten Speicherplatz im MSDTC-Protokoll handelt. Ein Beispiel für diese Verwendung ist das Web-Front-End einer Datenbank oder Anwendung, die eine Datenbank nutzt, die zu den von ihr bereitgestellten Diensten gehört.  
  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] verfügt über einen eigenen Satz Vertrauensebenen und ordnet diesen Vertrauensebenen über Richtliniendateien einen spezifischen Satz Berechtigungen zu. Weitere Informationen finden Sie unter [ASP.NET Trust Levels and Policy Files](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1). Wenn Sie das Windows-SDK installieren, werden die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Standardrichtliniendateien nicht <xref:System.Transactions.DistributedTransactionPermission>zugeordnet. Wenn Ihre Transaktion in einer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendung eskaliert wird, um vom MSDTC verwaltet zu werden, schlägt die Eskalation mit einer <xref:System.Security.SecurityException> fehl, sobald die <xref:System.Transactions.DistributedTransactionPermission>angefordert wird. Um die Transaktionseskalation in einer teilweise vertrauenswürdigen [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Umgebung zu ermöglichen, müssen Sie die <xref:System.Transactions.DistributedTransactionPermission> auf denselben Standardvertrauensebenen erteilen wie <xref:System.Data.SqlClient.SqlClientPermission>. Sie können entweder Ihre eigene benutzerdefinierte Vertrauensebene und Richtliniendatei konfigurieren, um die Eskalation zu ermöglichen, oder die Standardrichtliniendateien **Web_hightrust.config** und **Web_mediumtrust.config**ändern.  
  
 Um die Richtliniendateien zu ändern, fügen einen **SecurityClass** -Element für **von DistributedTransactionPermission** auf die **SecurityClasses** Element unter den  **PolicyLevel** Element, und fügen Sie ein entsprechendes **Ipermissions** Element unter den [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] **NamedPermissionSet** für System.Transactions hinzu. Die folgende Konfigurationsdatei veranschaulicht dies.  
  
```xml  
<SecurityClasses>  
   <SecurityClass Name="DistributedTransactionPermission" Description="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
...  
</SecurityClasses>  
  
<PermissionSet  
  class="NamedPermissionSet"  
  version="1"  
  Name="ASP.Net">  
     <IPermission  
        class="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
        version="1"  
        Unrestricted="true"  
     />  
...  
</PermissionSet>  
```  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Richtlinie zur Sicherheit finden Sie unter [SecurityPolicy-Element ((ASP.NET Settings Schema)](http://msdn.microsoft.com/library/469d8d22-d263-46bb-8400-40d8d027faba).  
  
## <a name="dynamic-compilation"></a>Dynamische Kompilierung  
 Wenn Sie <xref:System.Transactions> in eine [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendung, die bei Zugriff dynamisch kompiliert wird, importieren und dort verwenden möchten, sollten Sie einen Verweis auf die <xref:System.Transactions> -Assembly in die Konfigurationsdatei einfügen. Der Verweis sollte unterhalb des Abschnitts **compilation**/**assemblies** der **Web.config** -Konfigurationsdatei des Standardstammverzeichnisses oder der Konfigurationsdatei einer spezifischen Webanwendung hinzugefügt werden. Dies wird im folgenden Beispiel veranschaulicht:  
  
```xml  
<configuration>  
   <system.web>  
      <compilation>  
         <assemblies>  
      <add assembly="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
         </assemblies>  
      </compilation>  
   </system.web>  
</configuration>  
```  
  
 Weitere Informationen finden Sie unter [add-Element für zu kompilierende ((ASP.NET Settings Schema) Assemblys](http://msdn.microsoft.com/library/602197e8-108d-4249-b752-ba2a318f75e4).  
  
## <a name="see-also"></a>Siehe auch  
 [ASP.NET Vertrauensebenen und Richtliniendateien](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1)  
 [SecurityPolicy-Element ((ASP.NET Settings Schema)](http://msdn.microsoft.com/library/469d8d22-d263-46bb-8400-40d8d027faba)  
 [Eskalation der Transaktionsverwaltung](../../../../docs/framework/data/transactions/transaction-management-escalation.md)
