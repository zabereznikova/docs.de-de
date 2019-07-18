---
title: Verwenden von System.Transactions in ASP.NET
ms.date: 03/30/2017
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
ms.openlocfilehash: 866d7b69fa6c18f6edfb48655b213e140a095a28
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880220"
---
# <a name="using-systemtransactions-in-aspnet"></a>Verwenden von System.Transactions in ASP.NET
In diesem Thema wird beschrieben, wie Sie <xref:System.Transactions> in einer ASP.NET-Anwendung erfolgreich verwenden können.  
  
## <a name="enable-distributedtransactionpermission-in-aspnet"></a>Aktivieren von DistributedTransactionPermission in ASP.NET  
 <xref:System.Transactions> unterstützt teilweise vertrauenswürdige Aufrufer und wird mit dem **AllowPartiallyTrustedCallers** -Attribut (APTCA) markiert. Die Vertrauensebenen für <xref:System.Transactions> werden auf der Basis der Ressourcentypen (beispielsweise Systemspeicher, freigegebene prozessübergreifende Ressourcen, systemweite Ressourcen und andere Ressourcen) definiert, die <xref:System.Transactions> verfügbar macht, und auf der Basis der Vertrauensebene, die erforderlich sein soll, um auf diese Ressourcen zuzugreifen. In einer teilweise vertrauenswürdigen Umgebung kann eine nicht vollständig vertrauenswürdige Assembly Transaktionen nur innerhalb der Anwendungsdomäne nutzen (in diesem Fall ist die einzige geschützte Ressource der Systemspeicher), sofern ihr nicht die <xref:System.Transactions.DistributedTransactionPermission>erteilt wird.  
  
 <xref:System.Transactions.DistributedTransactionPermission> wird immer dann gefordert, wenn die Transaktionsverwaltung eskaliert wird, um vom Microsoft Distributed Transaction Coordinator (MSDTC) verwaltet zu werden. Diese Art des Szenarios verwendet prozessübergreifende Ressourcen und insbesondere eine globale Ressource, bei der es sich um den reservierten Speicherplatz im MSDTC-Protokoll handelt. Ein Beispiel für diese Verwendung ist das Web-Front-End einer Datenbank oder Anwendung, die eine Datenbank nutzt, die zu den von ihr bereitgestellten Diensten gehört.  
  
 ASP.NET verfügt über einen eigenen Satz Vertrauensebenen und ordnet diesen Vertrauensebenen über Richtliniendateien einen spezifischen Satz Berechtigungen zu. Weitere Informationen finden Sie unter [ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100)). Wenn Sie zunächst das Windows SDK installieren, keine der standardmäßigen ASP.NET Richtliniendateien zugeordnet sind die <xref:System.Transactions.DistributedTransactionPermission>. Wenn Ihre Transaktion in einer ASP.NET-Anwendung eskaliert wird, um vom MSDTC verwaltet zu werden, schlägt die Eskalation mit einer <xref:System.Security.SecurityException> fehl, sobald die <xref:System.Transactions.DistributedTransactionPermission> angefordert wird. Um die Transaktionseskalation in einer teilweise vertrauenswürdigen ASP.NET-Umgebung zu ermöglichen, müssen Sie die <xref:System.Transactions.DistributedTransactionPermission> auf denselben Vertrauensebenen erteilen wie <xref:System.Data.SqlClient.SqlClientPermission>. Sie können entweder Ihre eigene benutzerdefinierte Vertrauensebene und Richtliniendatei konfigurieren, um die Eskalation zu ermöglichen, oder die Standardrichtliniendateien **Web_hightrust.config** und **Web_mediumtrust.config**ändern.  
  
 Um die Richtliniendateien zu ändern, fügen einen **SecurityClass** -Element für **DistributedTransactionPermission** auf die **SecurityClasses** Element unter den  **PolicyLevel** Element, und fügen Sie ein entsprechendes **IPermission** -Element unterhalb des ASP.NET **NamedPermissionSet** für System.Transactions hinzu. Die folgende Konfigurationsdatei veranschaulicht dies.  
  
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
  
 Weitere Informationen über ASP.NET-Sicherheitsrichtlinien finden Sie unter [SecurityPolicy-Element ((ASP.NET Einstellungsschema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100)).  
  
## <a name="dynamic-compilation"></a>Dynamische Kompilierung  
 Wenn Sie <xref:System.Transactions> zur Verwendung in eine ASP.NET-Anwendung importieren möchten, die bei Zugriff dynamisch kompiliert wird, sollten Sie einen Verweis auf die <xref:System.Transactions>-Assembly in die Konfigurationsdatei einfügen. Der Verweis sollte unterhalb des Abschnitts **compilation**/**assemblies** der **Web.config** -Konfigurationsdatei des Standardstammverzeichnisses oder der Konfigurationsdatei einer spezifischen Webanwendung hinzugefügt werden. Dies wird im folgenden Beispiel veranschaulicht:  
  
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
  
 Weitere Informationen finden Sie unter [add-Element für zu kompilierende ((ASP.NET Einstellungsschema) Assemblys](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100)).  
  
## <a name="see-also"></a>Siehe auch

- [ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))
- [SecurityPolicy-Element ((ASP.NET Einstellungsschema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))
- [Eskalation der Transaktionsverwaltung](../../../../docs/framework/data/transactions/transaction-management-escalation.md)
