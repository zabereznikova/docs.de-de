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
ms.openlocfilehash: a0466eb5c24840c77a3b191f9b0e001f6b267fca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181163"
---
# <a name="link-demands"></a>Verknüpfungsaufrufe
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 Ein Linkaufruf (Verknüpfungsaufruf) bewirkt eine Sicherheitsüberprüfung während der Just-In-Time-Kompilierung, wobei nur die direkt aufrufende Assembly Ihres Codes überprüft wird. Das Verlinken erfolgt, wenn der Code an einen Typverweis, einschließlich Funktionszeigerverweise und Methodenaufrufe, gebunden wird. Hat die aufrufende Assembly keine ausreichende Berechtigung, Ihren Code zu verlinken, ist der Link unzulässig, und beim Laden und Ausführen des Codes wird eine Laufzeitausnahme ausgelöst.  Linkaufrufe können in Klassen, die von Ihrem Code erben, überschrieben werden.  
  
 Beachten Sie, dass bei diesem Typ von Forderung kein vollständiger Stackwalk durchgeführt wird und der Code weiterhin anfällig für Täuschungsmanöver ist. Wenn z. B. eine Methode in Assembly A durch einen Verknüpfungsanforderungen geschützt ist, wird ein direkter Aufrufer in Assembly B basierend auf den Berechtigungen von Assembly B ausgewertet.  Der Verknüpfungsbedarf wertet jedoch keine Methode in Assembly C aus, wenn die Methode in Assembly A unter Verwendung der Methode in Assembly B indirekt aufruft. Die Verknüpfungsanforderung gibt an, dass nur die Berechtigungen angegeben werden, die direkte Aufrufer in der sofort aufrufenden Assembly mit dem Code verknüpfen müssen. Er gibt nicht die Berechtigungen an, die alle Aufrufer haben müssen, um Ihren Code auszuführen.  
  
 Die Stackwalkmodifizierer <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A> und <xref:System.Security.CodeAccessPermission.PermitOnly%2A> haben keinen Einfluss auf die Auswertung von Linkaufrufen.  Da Linkaufrufe keinen Stackwalk ausführen, haben die Stackwalkmodifizierer keinen Einfluss auf Linkaufrufe.  
  
 Wenn über [Reflection](../reflection-and-codedom/reflection.md)auf eine Methode zugegriffen wird, die durch eine Verknüpfungsanforderung geschützt ist, überprüft eine Verknüpfungsanforderung den unmittelbaren Aufrufer des Codes, auf den durch Reflektion zugegriffen wird. Dies gilt sowohl für Methodenerkennungen als auch Methodenaufrufe, die über Reflektion ausgeführt werden. Angenommen, Code verwendet Reflektion, <xref:System.Reflection.MethodInfo> um ein Objekt zurückzugeben, das eine Methode darstellt, die durch eine Verknüpfungsanforderung geschützt ist, und übergibt das **MethodInfo-Objekt** dann an einen anderen Code, der das Objekt zum Aufrufen der ursprünglichen Methode verwendet. In diesem Fall erfolgt die Verknüpfungsanforderungsprüfung zweimal: einmal für den Code, der das **MethodInfo-Objekt** zurückgibt, und einmal für den Code, der es aufruft.  
  
> [!NOTE]
> Ein Linkaufruf, der für einen statischen Klassenkonstruktor durchgeführt wird, schützt diesen Konstruktor nicht, da statische Konstruktoren vom System außerhalb des Codeausführungspfades der Anwendung aufgerufen werden. Dies hat zur Folge, dass ein Linkaufruf, wenn er auf eine ganze Klasse angewendet wird, einen statischen Konstruktor nicht schützen kann, obwohl er der Rest der Klasse schützt.  
  
 Im folgenden Codefragment wird deklarativ angegeben, dass sämtlicher Code mit einer Verlinkung zur `ReadData`-Methode die `CustomPermission`-Berechtigung haben muss. Diese Berechtigung ist eine hypothetische benutzerdefinierte Berechtigung und nicht in .NET Framework vorhanden. Die Anforderung erfolgt durch Übergeben eines **SecurityAction.LinkDemand-Flags** an die `CustomPermissionAttribute`.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Attribute](../../standard/attributes/index.md)
- [Codezugriffssicherheit](code-access-security.md)
