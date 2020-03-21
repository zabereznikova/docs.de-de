---
title: 'Gewusst wie: Ausführen von teilweise vertrauenswürdigem Code in einer Sandbox'
ms.date: 03/30/2017
helpviewer_keywords:
- partially trusted code
- sandboxing
- partial trust
- restricted security environment
- code security, sandboxing
ms.assetid: d1ad722b-5b49-4040-bff3-431b94bb8095
ms.openlocfilehash: b2f5a72e747f6c71743a7b22fe9f1962ac2f6b53
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181179"
---
# <a name="how-to-run-partially-trusted-code-in-a-sandbox"></a>Gewusst wie: Ausführen von teilweise vertrauenswürdigem Code in einer Sandbox
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 Unter einer Sandkastenumgebung versteht man das Ausführen von Code in einer beschränkten Sicherheitsumgebung, in der die dem Code gewährten Zugriffsrechte eingeschränkt sind. Wenn Sie beispielsweise über eine verwaltete Bibliothek aus einer nicht vollständig vertrauenswürdigen Quelle verfügen, sollten Sie diese nicht als vollständig vertrauenswürdig ausführen. Stattdessen sollten Sie den Code in eine Sandkastenumgebung setzen, in der die Berechtigungen des Codes auf diejenigen beschränkt sind, die er voraussichtlich benötigt (z. B. die Berechtigung <xref:System.Security.Permissions.SecurityPermissionFlag.Execution>).  
  
 Sie können eine Sandkastenumgebung auch zum Testen von Code verwenden, den Sie verteilen und der in teilweise vertrauenswürdigen Umgebungen ausgeführt wird.  
  
 Eine <xref:System.AppDomain> ist eine effektive Methode zur Bereitstellung eines Sandkastens für verwaltete Anwendungen. Anwendungsdomänen, die für die Ausführung von teilweise vertrauenswürdigem Code verwendet werden, weisen Berechtigungen auf, die die geschützten Ressourcen definieren, die bei der Ausführung in dieser <xref:System.AppDomain> verfügbar sind. Code, der in der <xref:System.AppDomain> ausgeführt wird, ist von den Berechtigungen gebunden, die mit <xref:System.AppDomain> verbunden sind und darf nur auf die angegebenen Ressourcen zugreifen. Die <xref:System.AppDomain> enthält zudem auch ein <xref:System.Security.Policy.StrongName>-Array, das verwendet wird, um Assemblys zu identifizieren, die als vollständig vertrauenswürdig geladen werden sollen. Damit ist der Ersteller einer <xref:System.AppDomain> in der Lage, eine neue Sandkastendomäne zu starten, die dafür sorgt, dass bestimmte Hilfsassemblys als vollständig vertrauenswürdig gelten. Eine weitere Option zum Laden von Assemblys als vollständig vertrauenswürdig besteht darin, sie in den globalen Assemblycache zu setzen; damit werden Assemblys jedoch in allen Anwendungsdomänen als vollständig vertrauenswürdig geladen, die auf diesem Computer erstellt wurden. Die Liste der starken Namen unterstützt eine auf der jeweiligen <xref:System.AppDomain> basierende Entscheidung, mit der eine restriktivere Festlegung möglich ist.  
  
 Sie können die <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType>-Methodenüberladung verwenden, um die Berechtigung anzugeben, die für Anwendungen festgelegt werden, die in einer Sandkastenumgebung ausgeführt werden. Mit dieser Überladung sind Sie in der Lage, die exakte Ebene der gewünschten Codezugriffsicherheit festzulegen. Assemblys, die unter Verwendung dieser Überladung in eine <xref:System.AppDomain> geladen werden, können entweder über den angegebenen Berechtigungssatz verfügen oder als vollständig vertrauenswürdig gelten. Der Assembly wird volle Vertrauenswürdigkeit gewährt, wenn sie sich im globalen Assemblycache befindet oder im Arrayparameter `fullTrustAssemblies` (<xref:System.Security.Policy.StrongName>) aufgelistet ist. Nur Assemblys, die bekanntermaßen vollständig vertrauenswürdig sind, sollten der `fullTrustAssemblies`-Liste hinzugefügt werden.  
  
 Die Überladung hat die folgende Signatur:  
  
```csharp
AppDomain.CreateDomain( string friendlyName,  
                        Evidence securityInfo,  
                        AppDomainSetup info,  
                        PermissionSet grantSet,  
                        params StrongName[] fullTrustAssemblies);  
```  
  
 Die Parameter der <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29>-Methodenüberladung geben der Namen der <xref:System.AppDomain> an, den Beweis für die <xref:System.AppDomain>, das <xref:System.AppDomainSetup>-Objekt, das die Anwendungsbasis für den Sandkasten identifiziert, den zu verwendenden Berechtigungssatz und die starken Namen für vollständig vertrauenswürdige Assemblys.  
  
 Aus Sicherheitsgründen sollte die im `info`-Parameter angegebene Anwendungsbasis nicht die Anwendungsbasis der Hostanwendung sein.  
  
 Im `grantSet`-Parameter können Sie entweder einen Berechtigungssatz angeben, den Sie explizit erstellt haben, oder den standardmäßigen Berechtigungssatz, der von der <xref:System.Security.SecurityManager.GetStandardSandbox%2A>-Methode erstellt wurde.  
  
 Im Gegensatz zu den meisten <xref:System.AppDomain>-Ladungen wird der Beweis für die <xref:System.AppDomain> (der vom `securityInfo`-Parameter bereitgestellt wird) nicht zur Festlegung des Berechtigungssatzes für teilweise vertrauenswürdige Assemblys verwendet. Dieser wird stattdessen unabhängig vom `grantSet`-Parameter angegeben. Der Beweis kann jedoch für andere Zwecke wie der Festlegung des isolierten Speicherbereichs verwendet werden.  
  
### <a name="to-run-an-application-in-a-sandbox"></a>So führen Sie eine Anwendung in einer Sandkastenumgebung aus  
  
1. Erstellen Sie den Berechtigungssatz, der der nicht vertrauenswürdigen Anwendung gewährt werden soll. Die Mindestberechtigung, die Sie gewähren können, ist die Berechtigung <xref:System.Security.Permissions.SecurityPermissionFlag.Execution>. Sie können auch weitere Berechtigungen gewähren, von denen Sie annehmen, dass sie für nicht vertrauenswürdigen Code sicher sind, beispielsweise <xref:System.Security.Permissions.IsolatedStorageFilePermission>. Mit dem folgenden Code wird ein neuer Berechtigungssatz erstellt, der nur die Berechtigung <xref:System.Security.Permissions.SecurityPermissionFlag.Execution> enthält.  
  
    ```csharp
    PermissionSet permSet = new PermissionSet(PermissionState.None);  
    permSet.AddPermission(new SecurityPermission(SecurityPermissionFlag.Execution));  
    ```  
  
     Alternativ können Sie einen vorhandenen benannte Berechtigungssatz wie "Internet" verwenden.  
  
    ```csharp
    Evidence ev = new Evidence();  
    ev.AddHostEvidence(new Zone(SecurityZone.Internet));  
    PermissionSet internetPS = SecurityManager.GetStandardSandbox(ev);  
    ```  
  
     Die <xref:System.Security.SecurityManager.GetStandardSandbox%2A>-Methode gibt entweder einen `Internet`-Berechtigungssatz oder einen `LocalIntranet`-Berechtigungssatz zurück, abhängig von der im Beweis angegebenen Zone. <xref:System.Security.SecurityManager.GetStandardSandbox%2A> konstruiert zudem Identitätsberechtigungen für einige der Beweis-Objekte, die als Verweise übergeben werden.  
  
2. Signieren Sie die Assembly, die die Hostingklasse enthält (in diesem Beispiel `Sandboxer` genannt) und den nicht vertrauenswürdigen Code aufruft. Fügen Sie den <xref:System.Security.Policy.StrongName>, der zum Signieren der Assembly verwenden wird, zum <xref:System.Security.Policy.StrongName>-Array des `fullTrustAssemblies`-Parameters des <xref:System.AppDomain.CreateDomain%2A>-Aufrufs hinzu. Die Hostingklasse muss als vollständig vertrauenswürdig ausgeführt werden, um die Ausführung von teilweise vertrauenswürdigem Code zu ermöglichen oder um Dienste für die teilweise vertrauenswürdige Anwendung bereitzustellen. Und so lesen Sie den <xref:System.Security.Policy.StrongName> einer Assembly:  
  
    ```csharp
    StrongName fullTrustAssembly = typeof(Sandboxer).Assembly.Evidence.GetHostEvidence<StrongName>();  
    ```  
  
     .NET Framework-Assemblys wie mscorlib und System.dll müssen nicht zur Liste der vollständig vertrauenswürdigen Assemblys hinzugefügt werden, da sie als vollständig vertrauenswürdig aus dem globalen Assemblycache geladen werden.  
  
3. Initialisieren Sie den <xref:System.AppDomainSetup>-Parameter der <xref:System.AppDomain.CreateDomain%2A>-Methode. Mit diesem Parameter können Sie viele der Einstellungen der neuen <xref:System.AppDomain> steuern. Die <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft ist eine wichtige Einstellung und sollte sich von der <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft der <xref:System.AppDomain> der Hostanwendung unterscheiden. Wenn die <xref:System.AppDomainSetup.ApplicationBase%2A>-Einstellungen die gleichen sind, kann die teilweise vertrauenswürdige Anwendung bewirken, dass die Hostanwendung (als vollständig vertrauenswürdig) eine hiervon definierte Ausnahme lädt, wodurch sie angreifbar wird. Dies ist ein weiterer Grund warum ein Catch (Ausnahme) nicht zu empfehlen ist. Wird die Anwendungsbasis des Hosts anders als die Anwendungsbasis der Anwendung in der Sandboxumgebung eingestellt, verringert sich das Risiko von Angriffen.  
  
    ```csharp
    AppDomainSetup adSetup = new AppDomainSetup();  
    adSetup.ApplicationBase = Path.GetFullPath(pathToUntrusted);  
    ```  
  
4. Rufen Sie die <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29>-Methodenüberladung auf, um die Anwendungsdomäne mit den angegebenen Parametern zu erstellen.  
  
     Die Signatur für diese Methode lautet:  
  
    ```csharp
    public static AppDomain CreateDomain(string friendlyName,
        Evidence securityInfo, AppDomainSetup info, PermissionSet grantSet,
        params StrongName[] fullTrustAssemblies)  
    ```  
  
     Zusätzliche Informationen:  
  
    - Dies ist die einzige Überladung der <xref:System.AppDomain.CreateDomain%2A>-Methode, die einen <xref:System.Security.PermissionSet> als Parameter akzeptiert und daher die einzige Überladung, mit der Sie eine Anwendung in einer teilweise vertrauenswürdigen Umgebung laden können.  
  
    - Der `evidence`-Parameter wird nicht verwendet, um einen Berechtigungssatz zu berechnen; er wird für die Identifikation durch andere Features von .NET Framework verwendet.  
  
    - Die Festlegung der <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft des `info`-Parameters ist für diese Überladung obligatorisch.  
  
    - Der `fullTrustAssemblies`-Parameter weist das Schlüsselwort `params` auf, was bedeutet, dass es nicht notwendig ist, ein <xref:System.Security.Policy.StrongName>-Array zu erstellen. Die Übergabe von keinem, einem oder mehr starken Namen als Parameter ist zulässig.  
  
    - Der Code zum Erstellen der Anwendungdomäne ist folgender:  
  
    ```csharp
    AppDomain newDomain = AppDomain.CreateDomain("Sandbox", null, adSetup, permSet, fullTrustAssembly);  
    ```  
  
5. Laden Sie den Code in die <xref:System.AppDomain> der von Ihnen erstellten Sandkastenumgebung. Dies kann auf zwei Arten erfolgen:  
  
    - Rufen Sie die <xref:System.AppDomain.ExecuteAssembly%2A>-Methode für die Assembly auf.  
  
    - Verwenden Sie die <xref:System.Activator.CreateInstanceFrom%2A>-Methode, um in der neuen <xref:System.AppDomain> eine Instanz einer von <xref:System.MarshalByRefObject> abgeleiteten Klasse zu erstellen.  
  
     Die zweite Methode ist zu bevorzugen, da es hiermit einfacher ist, Parameter an die neue <xref:System.AppDomain>-Instanz zu übergeben. Die <xref:System.Activator.CreateInstanceFrom%2A>-Methode bieten zwei wichtige Funktionen:  
  
    - Sie können eine Codebasis verwenden, die auf einen Speicherort verweist, der nicht Ihre Assembly enthält.  
  
    - Sie können die Erstellung unter einem <xref:System.Security.CodeAccessPermission.Assert%2A> für vollständige Vertrauenswürdigkeit (<xref:System.Security.Permissions.PermissionState.Unrestricted?displayProperty=nameWithType>) vornehmen, wodurch Sie in der Lage sind, eine Instanz einer kritischen Klasse zu erstellen. (Dies geschieht immer dann, wenn Ihre Baugruppe keine Transparenzmarkierungen hat und als voll vertrauenswürdig geladen wird.) Daher müssen Sie darauf achten, nur Code zu erstellen, dem Sie mit dieser Funktion vertrauen, und es wird empfohlen, nur Instanzen vollständig vertrauenswürdiger Klassen in der neuen Anwendungsdomäne zu erstellen.  
  
    ```csharp
    ObjectHandle handle = Activator.CreateInstanceFrom(  
    newDomain, typeof(Sandboxer).Assembly.ManifestModule.FullyQualifiedName,  
           typeof(Sandboxer).FullName );  
    ```  
  
     Beachten Sie, dass die Klasse die <xref:System.MarshalByRefObject>-Klasse erweitern muss, damit eine Instanz einer Klasse in einer neuen Domäne erstellt werden kann.  
  
    ```csharp
    class Sandboxer:MarshalByRefObject  
    ```  
  
6. Entpacken Sie die neue Domäneninstanz in einen Verweis in dieser Domäne. Dieser Verweis wird verwendet, um den nicht vertrauenswürdigen Code auszuführen.  
  
    ```csharp
    Sandboxer newDomainInstance = (Sandboxer) handle.Unwrap();  
    ```  
  
7. Rufen Sie in der `ExecuteUntrustedCode`-Methode der Instanz der soeben erstellten `Sandboxer`-Klasse auf.  
  
    ```csharp
    newDomainInstance.ExecuteUntrustedCode(untrustedAssembly, untrustedClass, entryPoint, parameters);  
    ```  
  
     Dieser Aufruf wird in der Anwendungsdomäne in der Sandkastenumgebung ausgeführt, in der es nur eingeschränkte Berechtigungen gibt.  
  
    ```csharp
    public void ExecuteUntrustedCode(string assemblyName, string typeName, string entryPoint, Object[] parameters)  
    {  
        //Load the MethodInfo for a method in the new assembly. This might be a method you know, or
        //you can use Assembly.EntryPoint to get to the entry point in an executable.  
        MethodInfo target = Assembly.Load(assemblyName).GetType(typeName).GetMethod(entryPoint);  
        try  
        {  
            // Invoke the method.  
            target.Invoke(null, parameters);  
        }  
        catch (Exception ex)  
        {  
        //When information is obtained from a SecurityException extra information is provided if it is
        //accessed in full-trust.  
            new PermissionSet(PermissionState.Unrestricted).Assert();  
            Console.WriteLine("SecurityException caught:\n{0}", ex.ToString());  
            CodeAccessPermission.RevertAssert();  
            Console.ReadLine();  
        }  
    }  
    ```  
  
     <xref:System.Reflection> wird verwendet, um ein Handle von einer Methode in der teilweise vertrauenswürdigen Assembly zu erhalten. Das Handle kann verwendet werden, um Code auf sichere Weise mit minimalen Berechtigungen auszuführen.  
  
     Beachten Sie im vorherigen Code den <xref:System.Security.PermissionSet.Assert%2A> für die Berechtigung "Volle Vertrauenswürdigkeit", bevor Sie die <xref:System.Security.SecurityException> drucken.  
  
    ```csharp
    new PermissionSet(PermissionState.Unrestricted).Assert()  
    ```  
  
     Der Assert "Volle Vertrauenswürdigkeit" wird verwendet, um erweiterte Informationen zu der <xref:System.Security.SecurityException> zu erhalten. Ohne den <xref:System.Security.PermissionSet.Assert%2A> erkennt die <xref:System.Security.SecurityException.ToString%2A>-Methode der <xref:System.Security.SecurityException>, dass sich teilweise vertrauenswürdiger Code im Stack befindet und schränkt die zurückgegebenen Informationen ein. Dies kann zu Sicherheitsproblemen führen, wenn der teilweise vertrauenswürdige Code auf die Informationen zugreifen kann, das Risiko wird jedoch reduziert, indem keine <xref:System.Security.Permissions.UIPermission> gewährt wird. Der Assert "Volle Vertrauenswürdigkeit" sollte sparsam und nur dann verwendet werden, wenn Sie sicher sind, dass Sie teilweise vertrauenswürdigem Code nicht gestatten, auf volle Vertrauenswürdigkeit zu erhöhen. Als Regel gilt: Rufen Sie keinen Code, dem Sie nicht vertrauen, in derselben Funktion auf und nachdem einen Assert für volle Vertrauenswürdigkeit aufgerufen haben. Es hat sich bewährt, den Assert immer zurückzusetzen, wenn Sie ihn nicht mehr benötigen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Prozedur aus dem vorherigen Abschnitt implementiert. Im Beispiel enthält ein Projekt mit Namen `Sandboxer` in einer Visual Studio-Lösung auch ein Projekt namens `UntrustedCode`, das die Klasse `UntrustedClass` implementiert. Bei diesem Szenario wird davon ausgegangen, dass Sie eine Bibliotheksassembly heruntergeladen haben, die eine Methode enthält, von der erwartet wird, dass sie `true` oder `false` zurückgibt, um anzugeben, ob es sich bei der von Ihnen eingegebenen Zahl um eine Fibonacci-Zahl handelt. Stattdessen versucht die Methode, eine Datei auf Ihrem Computer zu lesen. Das folgende Beispiel zeigt den nicht vertrauenswürdigen Code.  
  
```csharp
using System;  
using System.IO;  
namespace UntrustedCode  
{  
    public class UntrustedClass  
    {  
        // Pretend to be a method checking if a number is a Fibonacci  
        // but which actually attempts to read a file.  
        public static bool IsFibonacci(int number)  
        {  
           File.ReadAllText("C:\\Temp\\file.txt");  
           return false;  
        }  
    }  
}  
```  
  
 Das folgende Beispiel zeigt den `Sandboxer`-Anwendungscode, der den nicht vertrauenswürdigen Code ausführt.  
  
```csharp
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.IO;  
using System.Security;  
using System.Security.Policy;  
using System.Security.Permissions;  
using System.Reflection;  
using System.Runtime.Remoting;  
  
//The Sandboxer class needs to derive from MarshalByRefObject so that we can create it in another
// AppDomain and refer to it from the default AppDomain.  
class Sandboxer : MarshalByRefObject  
{  
    const string pathToUntrusted = @"..\..\..\UntrustedCode\bin\Debug";  
    const string untrustedAssembly = "UntrustedCode";  
    const string untrustedClass = "UntrustedCode.UntrustedClass";  
    const string entryPoint = "IsFibonacci";  
    private static Object[] parameters = { 45 };  
    static void Main()  
    {  
        //Setting the AppDomainSetup. It is very important to set the ApplicationBase to a folder
        //other than the one in which the sandboxer resides.  
        AppDomainSetup adSetup = new AppDomainSetup();  
        adSetup.ApplicationBase = Path.GetFullPath(pathToUntrusted);  
  
        //Setting the permissions for the AppDomain. We give the permission to execute and to
        //read/discover the location where the untrusted code is loaded.  
        PermissionSet permSet = new PermissionSet(PermissionState.None);  
        permSet.AddPermission(new SecurityPermission(SecurityPermissionFlag.Execution));  
  
        //We want the sandboxer assembly's strong name, so that we can add it to the full trust list.  
        StrongName fullTrustAssembly = typeof(Sandboxer).Assembly.Evidence.GetHostEvidence<StrongName>();  
  
        //Now we have everything we need to create the AppDomain, so let's create it.  
        AppDomain newDomain = AppDomain.CreateDomain("Sandbox", null, adSetup, permSet, fullTrustAssembly);  
  
        //Use CreateInstanceFrom to load an instance of the Sandboxer class into the  
        //new AppDomain.
        ObjectHandle handle = Activator.CreateInstanceFrom(  
            newDomain, typeof(Sandboxer).Assembly.ManifestModule.FullyQualifiedName,  
            typeof(Sandboxer).FullName  
            );  
        //Unwrap the new domain instance into a reference in this domain and use it to execute the
        //untrusted code.  
        Sandboxer newDomainInstance = (Sandboxer) handle.Unwrap();  
        newDomainInstance.ExecuteUntrustedCode(untrustedAssembly, untrustedClass, entryPoint, parameters);  
    }  
    public void ExecuteUntrustedCode(string assemblyName, string typeName, string entryPoint, Object[] parameters)  
    {  
        //Load the MethodInfo for a method in the new Assembly. This might be a method you know, or
        //you can use Assembly.EntryPoint to get to the main function in an executable.  
        MethodInfo target = Assembly.Load(assemblyName).GetType(typeName).GetMethod(entryPoint);  
        try  
        {  
            //Now invoke the method.  
            bool retVal = (bool)target.Invoke(null, parameters);  
        }  
        catch (Exception ex)  
        {  
            // When we print informations from a SecurityException extra information can be printed if we are
            //calling it with a full-trust stack.  
            new PermissionSet(PermissionState.Unrestricted).Assert();  
            Console.WriteLine("SecurityException caught:\n{0}", ex.ToString());  
            CodeAccessPermission.RevertAssert();  
            Console.ReadLine();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Richtlinien für das Schreiben von sicherem Code](../../standard/security/secure-coding-guidelines.md)
