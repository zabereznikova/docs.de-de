---
title: Richtlinien für das Schreiben von sicherem, nicht verwaltetem Code
ms.date: 03/30/2017
helpviewer_keywords:
- code security, unmanaged code
- unmanaged code, securing
- security [.NET Framework], unmanaged code
- secure coding, unmanaged code
ms.assetid: a8d15139-d368-4c9c-a747-ba757781117c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 867157b329218b79c8cc1255b2158bbe83666531
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71045365"
---
# <a name="secure-coding-guidelines-for-unmanaged-code"></a>Richtlinien für das Schreiben von sicherem, nicht verwaltetem Code
Bestimmter Bibliothekscode muss nicht verwalteten Code aufrufen (z. B. APIs in systemeigenem Code, etwa Win32). Hierbei ist größte Vorsicht geboten, denn dies bedeutet, dass der Sicherheitsbereich für verwalteten Code verlassen wird. Wenn Ihr Code sicherheitsneutral ist, müssen sowohl Ihr Code als auch jeder Code, der Ihren Code aufruft, eine Berechtigung für nicht verwalteten Code haben (<xref:System.Security.Permissions.SecurityPermission> mit angegebenem <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> -Flag).  
  
 Häufig ist es jedoch nicht sinnvoll, dem Aufrufer so weit reichende Berechtigungen zu gewähren. In solchen Fällen kann Ihr vertrauenswürdiger Code das Bindeglied sein, vergleichbar mit dem verwalteten Wrapper- oder Bibliothekscode, der unter [Sichern von Wrappercode](../misc/securing-wrapper-code.md)beschrieben ist. Wenn die Funktionalität des zugrunde liegenden nicht verwalteten Codes vollständig sicher ist, kann dieser direkt verfügbar gemacht werden. Andernfalls ist zuerst eine geeignete Berechtigungsüberprüfung (Forderung) erforderlich.  
  
 Wenn Ihr Code nicht verwalteten Code aufruft, Sie aber nicht möchten, dass ein Aufrufer die Berechtigung zum Zugriff auf nicht verwalteten Code haben muss, müssen Sie diese Berechtigung bestätigen. Eine Bestätigung blockiert den Stackwalk entsprechend Ihrem Rahmen. Sie müssen vorsichtig sein, dass Sie keine Sicherheitslücke in diesem Prozess erstellen. In der Regel bedeutet dies, dass Sie eine geeignete Berechtigung für Aufrufer fordern und dann nicht verwalteten Code verwenden, um nur genau die Aktionen auszuführen, die durch diese Berechtigung zugelassen sind. In einigen Fällen (z. B. eine Funktion zum Abrufen der Tageszeit) kann nicht verwalteter Code direkt ohne Sicherheitsüberprüfungen verfügbar gemacht werden. In jedem Fall muss jeglicher Code, der eine Bestätigung gibt, die Sicherheit gewährleisten.  
  
 Da verwalteter Code, der einen Codepfad zu systemeigenem Code bereitstellt, ein potenzielles Ziel für Schadsoftware ist, muss mit besonderer Sorgfalt ermittelt werden, welcher Code sicher verwendet werden kann und wie dieser Code zu verwenden ist. Üblicherweise sollte nicht verwalteter Code nie direkt für teilweise vertrauenswürdige Aufrufer verfügbar gemacht werden. Es gibt zwei Hauptaspekte für die Bewertung der Sicherheit des Verwendens von nicht verwaltetem Code in Bibliotheken, die von teilweise vertrauenswürdigem Code aufgerufen werden können:  
  
- **Funktionalität**. Stellt die nicht verwaltete API Funktionen bereit, die Aufrufer daran hindern, potenziell gefährliche Vorgänge auszuführen? Für Codezugriffssicherheit werden Berechtigungen verwendet, um Zugriff auf Ressourcen zu erzwingen. Ermitteln Sie also, ob die API Dateien, eine Benutzeroberfläche oder Threading verwendet oder ob sie geschützte Informationen verfügbar macht. Ist dies der Fall ist, muss der verwaltete Code, in den die API eingebettet ist, die erforderlichen Berechtigungen anfordern, bevor zugelassen wird, dass sie ausgeführt wird. Darüber hinaus muss Speicherzugriff, solange er nicht durch eine Berechtigung geschützt ist, auf strikte Typsicherheit beschränkt werden.  
  
- **Parameterüberprüfung**. Bei einem verbreiteten Angriff werden unerwartete Parameter an verfügbar gemachte nicht verwaltete API-Methoden übergeben, um diese zu einer nicht ordnungsgemäßen Ausführung zu veranlassen. Pufferüberläufe mit bereichsüberschreitenden Index- oder Offsetwerten sind ein typisches Beispiel für diese Art von Angriffen wie auch jegliche Parameter, die möglicherweise einen Fehler im zugrunde liegenden Code ausnutzen. Daher muss verwalteter Code selbst dann, wenn der nicht verwaltete Code einer API (nach den nötigen Anforderungen) für teilweise vertrauenswürdige Aufrufer funktional sicher ist, auch umfassend die Parametergültigkeit prüfen, um sicherzustellen, dass aus Schadsoftware keine unbeabsichtigten Aufrufe möglich sind, indem die Wrapperebene von verwaltetem Code verwendet wird.  
  
## <a name="using-suppressunmanagedcodesecurityattribute"></a>Verwenden von SuppressUnmanagedCodeSecurityAttribute  
 Für ein Bestätigen und anschließendes Aufrufen von nicht verwaltetem Code ist ein Leistungsaspekt zu beachten. Für jeden solchen Aufruf fordert das Sicherheitssystem automatisch die Berechtigung für den nicht verwalteten Code an, wodurch jedes Mal ein Stackwalk ausgelöst wird. Wenn Sie nicht verwalteten Code bestätigen und sofort aufrufen, kann der Stackwalk bedeutungslos sein: Er besteht aus Ihrer Bestätigung und Ihrem Aufruf des nicht verwalteten Codes.  
  
 Das benutzerdefinierte Attribut <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> kann auf Einstiegspunkte von nicht verwaltetem Code angewendet werden, um die normale Sicherheitsüberprüfung zu deaktivieren, die von <xref:System.Security.Permissions.SecurityPermission> mit angegebener <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> -Berechtigung gefordert wird. Für diese Vorgehensweise ist immer äußerste Vorsicht geboten, da diese Aktion eine offene Tür für nicht verwalteten Code ohne Runtime-Sicherheitsüberprüfungen zur Folge hat. Beachten Sie, dass selbst bei Anwendung des **SuppressUnmanagedCodeSecurityAttribute** -Attributs eine einmalige Sicherheitsüberprüfung erfolgt, die bei der JIT-Kompilierung (Just-in-Time) vorgenommen wird, um sicherzustellen, dass der unmittelbare Aufrufer die Berechtigung zum Aufrufen von nicht verwaltetem Code hat.  
  
 Wenn Sie **SuppressUnmanagedCodeSecurityAttribute**verwenden, sollten Sie die folgenden Punkte überprüfen:  
  
- Definieren Sie den Einstiegspunkt in nicht verwalteten Code so, dass er intern ist oder außerhalb Ihres Codes auf andere Weise nicht zugänglich ist.  
  
- Jeder Aufruf von nicht verwaltetem Code ergibt eine potenzielle Sicherheitslücke. Vergewissern Sie sich, dass Ihr Code kein Zugang für Schadsoftware ist, um indirekt nicht verwalteten Code aufzurufen und eine Sicherheitsüberprüfung zu umgehen. Fordern Sie ggf. Berechtigungen an.  
  
- Verwenden Sie eine Benennungskonvention, um explizit erkennen zu können, ob Sie einen gefährlichen Pfad zu nicht verwaltetem Code erstellen, wie dies in diesem Abschnitt weiter unten beschrieben ist.  
  
## <a name="naming-convention-for-unmanaged-code-methods"></a>Benennungskonventionen für Methoden in nicht verwaltetem Code  
 Für das Benennen von Methoden in nicht verwaltetem Code hat sich eine praktische und empfehlenswerte Konvention bewährt. Alle Methoden in nicht verwaltetem Code werden in drei Kategorien unterteilt: **safe**, **native**, und **unsafe**. Diese Schlüsselwörter können als Namen von Klassen verwendet werden, in denen die verschiedenen Arten von Einstiegspunkten für nicht verwalteten Code definiert sind. In Quellcode sollten diese Schlüsselwörter dem jeweiligen Klassennamen hinzugefügt werden, wie beispielsweise in `Safe.GetTimeOfDay`, `Native.Xyz`oder `Unsafe.DangerousAPI`. Jedes dieser Schlüsselwörter bietet nützliche Sicherheitsinformationen für Entwickler, die diese Klasse verwenden, wie in der folgenden Tabelle beschrieben.  
  
|Stichwort|Sicherheitsüberlegungen|  
|-------------|-----------------------------|  
|**safe**|Absolut ungefährlich für den Aufruf durch Code, selbst bei Schadsoftware. Kann wie jeder andere verwaltete Code verwendet werden. Beispielsweise ist eine Funktion, die die Tageszeit abruft, üblicherweise sicher.|  
|**native**|Sicherheitsneutraler Code, d. h. nicht verwalteter Code, der von nicht verwaltetem Code eine Berechtigung zum Aufruf erfordert. Die Sicherheit wird überprüft, wodurch ein nicht berechtigter Aufrufer gestoppt wird.|  
|**unsafe**|Einstiegspunkt mit unterdrückter Sicherheit für potenziell gefährlichen nicht verwalteten Code . Entwickler sollten äußerst vorsichtig sein, wenn solcher nicht verwalteter Code verwendet wird, und sie sollten sicherstellen, dass andere Schutzmechanismen greifen, damit ein Sicherheitsrisiko vermieden wird. Entwickler müssen überlegt vorgehen, denn dieses Schlüsselwort setzt das Sicherheitssystem außer Kraft.|  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für das Schreiben von sicherem Code](../../standard/security/secure-coding-guidelines.md)
