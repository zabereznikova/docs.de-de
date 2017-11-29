---
title: "Verknüpfungsaufrufe"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], demands
- demanded permissions
- permissions [.NET Framework], demands
- granting permissions, demands
- code access security, demands
- user demands for permission
- caller security checks
- link demands
ms.assetid: a33fd5f9-2de9-4653-a4f0-d9df25082c4d
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: faeeabeda89ea233e67b66b8848f5bbb665d3804
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="link-demands"></a>Verknüpfungsaufrufe
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 Ein Linkaufruf (Verknüpfungsaufruf) bewirkt eine Sicherheitsüberprüfung während der Just-In-Time-Kompilierung, wobei nur die direkt aufrufende Assembly Ihres Codes überprüft wird. Das Verlinken erfolgt, wenn der Code an einen Typverweis, einschließlich Funktionszeigerverweise und Methodenaufrufe, gebunden wird. Hat die aufrufende Assembly keine ausreichende Berechtigung, Ihren Code zu verlinken, ist der Link unzulässig, und beim Laden und Ausführen des Codes wird eine Laufzeitausnahme ausgelöst.  Linkaufrufe können in Klassen, die von Ihrem Code erben, überschrieben werden.  
  
 Beachten Sie, dass bei diesem Typ von Forderung kein vollständiger Stackwalk durchgeführt wird und der Code weiterhin anfällig für Täuschungsmanöver ist. Z. B. wenn eine Methode in Assembly A durch einen Linkaufruf geschützt ist, wird ein direkter Aufrufer in Assembly B ausgewertet anhand der Berechtigungen von Assembly B.  Der Linkaufruf wertet jedoch keine Methode in Assembly C aus, wenn in der Assembly, die mit der Methode in Assembly b indirekt die Methode aufgerufen Der Linkaufruf gibt nur die Berechtigungen direkte Aufrufer in der unmittelbar aufrufenden Assembly benötigen, um für Ihren Code zu verknüpfen. Er gibt nicht die Berechtigungen an, die alle Aufrufer haben müssen, um Ihren Code auszuführen.  
  
 Die Stackwalkmodifizierer <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A> und <xref:System.Security.CodeAccessPermission.PermitOnly%2A> haben keinen Einfluss auf die Auswertung von Linkaufrufen.  Da Linkaufrufe keinen Stackwalk ausführen, haben die Stackwalkmodifizierer keinen Einfluss auf Linkaufrufe.  
  
 Wenn eine durch einen Linkaufruf geschützte Methode, über zugegriffen wird [Reflektion](../../../docs/framework/reflection-and-codedom/reflection.md), prüft ein Linkaufruf den direkten Aufrufer des Codes, auf den über Reflektion ermöglicht. Dies gilt sowohl für Methodenerkennungen als auch Methodenaufrufe, die über Reflektion ausgeführt werden. Nehmen wir beispielsweise an, Code verwendet Reflektion zum Zurückgeben einer <xref:System.Reflection.MethodInfo> durch einen Linkaufruf geschützte Methode darstellt, und übergibt dieses Objekt **MethodInfo** Objekt an anderen Code, der das Objekt verwendet wird, um die ursprüngliche Methode aufzurufen. In diesem Fall die linkaufrufüberprüfung zweimal durchgeführt: einmal für den Code, der gibt die **MethodInfo** Objekt und einmal für den Code, der es aufruft.  
  
> [!NOTE]
>  Ein Linkaufruf, der für einen statischen Klassenkonstruktor durchgeführt wird, schützt diesen Konstruktor nicht, da statische Konstruktoren vom System außerhalb des Codeausführungspfades der Anwendung aufgerufen werden. Dies hat zur Folge, dass ein Linkaufruf, wenn er auf eine ganze Klasse angewendet wird, einen statischen Konstruktor nicht schützen kann, obwohl er der Rest der Klasse schützt.  
  
 Im folgenden Codefragment wird deklarativ angegeben, dass sämtlicher Code mit einer Verlinkung zur `ReadData`-Methode die `CustomPermission`-Berechtigung haben muss. Diese Berechtigung ist eine hypothetische benutzerdefinierte Berechtigung und nicht in .NET Framework vorhanden. Die Forderung wird vorgenommen, durch das Übergeben einer **SecurityAction.LinkDemand** flag auf die `CustomPermissionAttribute`.  
  
```vb  
<CustomPermissionAttribute(SecurityAction.LinkDemand)> _  
Public Shared Function ReadData() As String  
    ' Access a custom resource.  
End Function    
```  
  
```csharp  
[CustomPermissionAttribute(SecurityAction.LinkDemand)]  
public static string ReadData()  
{  
    // Access a custom resource.  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Attribute](../../../docs/standard/attributes/index.md)  
 [Codezugriffssicherheit](../../../docs/framework/misc/code-access-security.md)
