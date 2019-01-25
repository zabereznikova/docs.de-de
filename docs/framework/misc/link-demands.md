---
title: Verknüpfungsaufrufe
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2f55e282309d21b78c0aad9e7ada687f23628379
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725674"
---
# <a name="link-demands"></a>Verknüpfungsaufrufe
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 Ein Linkaufruf (Verknüpfungsaufruf) bewirkt eine Sicherheitsüberprüfung während der Just-In-Time-Kompilierung, wobei nur die direkt aufrufende Assembly Ihres Codes überprüft wird. Das Verlinken erfolgt, wenn der Code an einen Typverweis, einschließlich Funktionszeigerverweise und Methodenaufrufe, gebunden wird. Hat die aufrufende Assembly keine ausreichende Berechtigung, Ihren Code zu verlinken, ist der Link unzulässig, und beim Laden und Ausführen des Codes wird eine Laufzeitausnahme ausgelöst.  Linkaufrufe können in Klassen, die von Ihrem Code erben, überschrieben werden.  
  
 Beachten Sie, dass bei diesem Typ von Forderung kein vollständiger Stackwalk durchgeführt wird und der Code weiterhin anfällig für Täuschungsmanöver ist. Z. B. wenn eine Methode in Assembly A durch einen Linkaufruf geschützt ist, wird ein direkter Aufrufer in Assembly B ausgewertet anhand der Berechtigungen von Assembly B.  Der Linkaufruf wertet jedoch keine Methode in Assembly C aus, wenn in der Assembly, die mit der Methode in Assembly b indirekt die-Methode aufgerufen Der Linkaufruf gibt an, dass nur die Berechtigungen leiten, dass der Aufrufer in der unmittelbar aufrufenden Assembly verfügen müssen, um mit Ihrem Code zu verknüpfen. Er gibt nicht die Berechtigungen an, die alle Aufrufer haben müssen, um Ihren Code auszuführen.  
  
 Die Stackwalkmodifizierer <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A> und <xref:System.Security.CodeAccessPermission.PermitOnly%2A> haben keinen Einfluss auf die Auswertung von Linkaufrufen.  Da Linkaufrufe keinen Stackwalk ausführen, haben die Stackwalkmodifizierer keinen Einfluss auf Linkaufrufe.  
  
 Wenn eine durch einen Linkaufruf geschützte Methode, über zugegriffen wird [Reflektion](../../../docs/framework/reflection-and-codedom/reflection.md), und klicken Sie dann ein Linkaufruf den direkten Aufrufer des Codes, auf den über Reflektion überprüft. Dies gilt sowohl für Methodenerkennungen als auch Methodenaufrufe, die über Reflektion ausgeführt werden. Nehmen wir beispielsweise an, die Code unter Verwendung von Reflektion ein <xref:System.Reflection.MethodInfo> -Objekt durch einen Linkaufruf geschützt, eine Methode darstellt, und übergibt, die dann **MethodInfo** Objekt, das einen anderen Code, der das Objekt wird verwendet, um die ursprüngliche Methode aufzurufen. In diesem Fall die linkaufrufüberprüfung zweimal: einmal für den Code, der gibt die **MethodInfo** -Objekt und einmal für den Code, den sie aufruft.  
  
> [!NOTE]
>  Ein Linkaufruf, der für einen statischen Klassenkonstruktor durchgeführt wird, schützt diesen Konstruktor nicht, da statische Konstruktoren vom System außerhalb des Codeausführungspfades der Anwendung aufgerufen werden. Dies hat zur Folge, dass ein Linkaufruf, wenn er auf eine ganze Klasse angewendet wird, einen statischen Konstruktor nicht schützen kann, obwohl er der Rest der Klasse schützt.  
  
 Im folgenden Codefragment wird deklarativ angegeben, dass sämtlicher Code mit einer Verlinkung zur `ReadData`-Methode die `CustomPermission`-Berechtigung haben muss. Diese Berechtigung ist eine hypothetische benutzerdefinierte Berechtigung und nicht in .NET Framework vorhanden. Die Forderung wird vorgenommen, indem Sie übergeben eine **SecurityAction.LinkDemand** flag, das die `CustomPermissionAttribute`.  
  
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
- [Attribute](../../../docs/standard/attributes/index.md)
- [Codezugriffssicherheit](../../../docs/framework/misc/code-access-security.md)
