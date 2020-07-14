---
title: Verknüpfungsaufrufe
description: Informieren Sie sich über Link Aufrufe, die eine Sicherheitsüberprüfung während der Just-in-time (JIT)-Kompilierung verursachen, und untersuchen Sie nur die sofortige aufrufende Assembly des Codes.
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
ms.openlocfilehash: cd89c4ef27abb92fba567a1f3b490cb9d78fdddd
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2020
ms.locfileid: "86282057"
---
# <a name="link-demands"></a>Verknüpfungsaufrufe
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 Ein Linkaufruf (Verknüpfungsaufruf) bewirkt eine Sicherheitsüberprüfung während der Just-In-Time-Kompilierung, wobei nur die direkt aufrufende Assembly Ihres Codes überprüft wird. Das Verlinken erfolgt, wenn der Code an einen Typverweis, einschließlich Funktionszeigerverweise und Methodenaufrufe, gebunden wird. Hat die aufrufende Assembly keine ausreichende Berechtigung, Ihren Code zu verlinken, ist der Link unzulässig, und beim Laden und Ausführen des Codes wird eine Laufzeitausnahme ausgelöst.  Linkaufrufe können in Klassen, die von Ihrem Code erben, überschrieben werden.  
  
 Beachten Sie, dass bei diesem Typ von Forderung kein vollständiger Stackwalk durchgeführt wird und der Code weiterhin anfällig für Täuschungsmanöver ist. Wenn eine Methode in Assembly a z. b. durch einen Link Aufruf geschützt ist, wird ein direkter Aufrufer in Assembly b basierend auf den Berechtigungen von Assembly b ausgewertet.  Der Link Aufruf wertet jedoch keine Methode in Assembly C aus, wenn er die Methode in Assembly a mithilfe der-Methode in Assembly B indirekt aufruft. Der Link Aufruf gibt nur die Berechtigungen an, die direkte Aufrufer in der unmittelbaren aufrufenden Assembly zum Verknüpfen mit dem Code benötigen. Er gibt nicht die Berechtigungen an, die alle Aufrufer haben müssen, um Ihren Code auszuführen.  
  
 Die Stackwalkmodifizierer <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A> und <xref:System.Security.CodeAccessPermission.PermitOnly%2A> haben keinen Einfluss auf die Auswertung von Linkaufrufen.  Da Linkaufrufe keinen Stackwalk ausführen, haben die Stackwalkmodifizierer keinen Einfluss auf Linkaufrufe.  
  
 Wenn auf eine durch einen Link Aufruf geschützte Methode über [Reflektion](../reflection-and-codedom/reflection.md)zugegriffen wird, überprüft ein Link Aufruf den unmittelbaren Aufrufer des Codes, auf den über Reflektion zugegriffen wird. Dies gilt sowohl für Methodenerkennungen als auch Methodenaufrufe, die über Reflektion ausgeführt werden. Angenommen, Code verwendet Reflektion, um ein-Objekt zurückzugeben, <xref:System.Reflection.MethodInfo> das eine durch einen Link Aufruf geschützte Methode darstellt, und übergibt dieses **MethodInfo** -Objekt dann an einen anderen Code, der das-Objekt verwendet, um die ursprüngliche Methode aufzurufen. In diesem Fall erfolgt die Überprüfung des Link Bedarfs zweimal: einmal für den Code, der das **MethodInfo** -Objekt zurückgibt, und einmal für den Code, der es aufruft.  
  
> [!NOTE]
> Ein Linkaufruf, der für einen statischen Klassenkonstruktor durchgeführt wird, schützt diesen Konstruktor nicht, da statische Konstruktoren vom System außerhalb des Codeausführungspfades der Anwendung aufgerufen werden. Dies hat zur Folge, dass ein Linkaufruf, wenn er auf eine ganze Klasse angewendet wird, einen statischen Konstruktor nicht schützen kann, obwohl er der Rest der Klasse schützt.  
  
 Im folgenden Codefragment wird deklarativ angegeben, dass sämtlicher Code mit einer Verlinkung zur `ReadData`-Methode die `CustomPermission`-Berechtigung haben muss. Diese Berechtigung ist eine hypothetische benutzerdefinierte Berechtigung und nicht in .NET Framework vorhanden. Die Anforderung erfolgt durch Übergeben eines **SecurityAction. LinkDemand** -Flags an den `CustomPermissionAttribute` .  
  
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

- [Attribute](../../standard/attributes/index.md)
- [Codezugriffssicherheit](code-access-security.md)
