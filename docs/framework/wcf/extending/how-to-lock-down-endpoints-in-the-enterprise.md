---
title: 'Vorgehensweise: Sperren von Endpunkten im Unternehmen'
ms.date: 03/30/2017
ms.assetid: 1b7eaab7-da60-4cf7-9d6a-ec02709cf75d
ms.openlocfilehash: fb9232c98f672701c60fa9228bb34d7b24d52330
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796968"
---
# <a name="how-to-lock-down-endpoints-in-the-enterprise"></a>Vorgehensweise: Sperren von Endpunkten im Unternehmen

Von Großunternehmen wird oft gefordert, dass Anwendungen unter Einhaltung der Sicherheitsrichtlinien der Unternehmen entwickelt werden. Im folgenden Thema wird erläutert, wie Sie ein clientend Punkt Validierungs Steuerelement entwickeln und installieren, das zum Überprüfen aller auf Computern installierten Windows Communication Foundation (WCF)-Client Anwendungen verwendet werden kann.

In diesem Fall ist das Validierungs Steuerelement eine Client Bestätigung, da dieses Endpunkt Verhalten dem Client [ \<commonbehavior->](../../configure-apps/file-schema/wcf/commonbehaviors.md) Abschnitt in der Datei Machine. config hinzugefügt wird. WCF lädt allgemeine Endpunkt Verhalten nur für Client Anwendungen und lädt allgemeine Dienst Verhaltensweisen nur für Dienst Anwendungen. Um diese Bestätigung für Dienstanwendungen installieren zu können, muss es sich bei der Bestätigung um ein Dienstverhalten handeln. Weitere Informationen finden Sie im [ \<Abschnitt "commonverhaltens>](../../configure-apps/file-schema/wcf/commonbehaviors.md) ".

> [!IMPORTANT]
> Dienst-oder Endpunkt Verhaltensweisen, <xref:System.Security.AllowPartiallyTrustedCallersAttribute> die nicht mit dem-Attribut (APTCA) markiert sind und dem [ \<commonverhaltens>](../../configure-apps/file-schema/wcf/commonbehaviors.md) Abschnitt einer Konfigurationsdatei hinzugefügt wurden, werden nicht ausgeführt, wenn die Anwendung in einer teilweise vertrauenswürdigen Umgebung ausgeführt wird, und Nein. eine Ausnahme wird ausgelöst, wenn dies auftritt. Um die Ausführung gemeinsamer Verhalten, wie z.&#160;B. Bestätigungen, zu erzwingen, müssen Sie einen der beiden folgenden Schritte ausführen:
>
> - Markieren Sie das allgemeine Verhalten mit <xref:System.Security.AllowPartiallyTrustedCallersAttribute> dem-Attribut, damit es ausgeführt werden kann, wenn es als teilweise vertrauenswürdige Anwendung bereitgestellt wird. Beachten Sie, dass auf dem Computer ein Registrierungseintrag festgelegt werden kann, um die Ausführung von mit APTCA markierten Assemblys zu verhindern.
>
> - Stellen Sie sicher, dass die Anwendung, wenn die Anwendung als voll vertrauenswürdige Anwendung bereitgestellt wird, die Sicherheitseinstellungen für den Code Zugriff nicht ändern kann, um die Anwendung in einer teilweise vertrauenswürdigen Umgebung auszuführen. Wenn sie dies können, dann wird die benutzerdefinierte Bestätigung nicht ausgeführt, und es wird keine Ausnahme ausgelöst. Eine Möglichkeit, dies sicherzustellen, finden Sie `levelfinal` unter der Option " [Code Zugriffs-Sicherheitsrichtlinien Tool (Caspol. exe)](https://go.microsoft.com/fwlink/?LinkId=248222)".
>
> Weitere Informationen finden Sie unter [teilweise vertrauenswürdige Best Practices](../feature-details/partial-trust-best-practices.md) und [unterstützte Bereitstellungs Szenarien](../feature-details/supported-deployment-scenarios.md).

### <a name="to-create-the-endpoint-validator"></a>So erstellen Sie eine Endpunktbestätigung

1. Erstellen Sie ein <xref:System.ServiceModel.Description.IEndpointBehavior> mit den gewünschten Validierungsschritten in der <xref:System.ServiceModel.Description.IEndpointBehavior.Validate%2A>-Methode. Der folgende Code veranschaulicht dies. (Das `InternetClientValidatorBehavior` wird aus dem Beispiel zur [Sicherheits](../samples/security-validation.md) Überprüfung entnommen.)

    [!code-csharp[LockdownValidation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorbehavior.cs#2)]

2. Erstellen Sie ein neues <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>, des die in Schritt 1 erstellte Endpunktbestätigung registriert. Dies wird im folgenden Codebeispiel gezeigt. (Der ursprüngliche Code für dieses Beispiel befindet sich im Beispiel zur [Sicherheits](../samples/security-validation.md) Überprüfung.)

    [!code-csharp[LockdownValidation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorelement.cs#3)]

3. Stellen Sie sicher, dass die kompilierte Assembly mit einem starken Namen signiert wird. Weitere Informationen finden Sie unter [Strong Name-Tool (SN). EXE)](https://go.microsoft.com/fwlink/?LinkId=248217) und den Compilerbefehlen für Ihre Sprache.

### <a name="to-install-the-validator-into-the-target-computer"></a>So installieren Sie die Bestätigung auf dem Zielcomputer

1. Installieren Sie die Endpunktbestätigung mithilfe des entsprechenden Mechanismus. In einem Unternehmen kann dies die Verwendung der Gruppenrichtlinie und des Systems Management Server (SMS) sein.

2. Installieren Sie die Assembly mit starkem Namen im globalen Assemblycache mithilfe von " [Gacutil. exe" (Tool für den globalen Assemblycache)](../../tools/gacutil-exe-gac-tool.md).

3. Verwenden Sie die <xref:System.Configuration?displayProperty=nameWithType>-Namespacetypen, um Folgendes durchzuführen:

    1. Fügen Sie die Erweiterung dem Abschnitt [ \<verhalteextensions >](../../configure-apps/file-schema/wcf/behaviorextensions.md) unter Verwendung eines voll qualifizierten Typnamens hinzu, und Sperren Sie das Element.

         [!code-csharp[LockdownValidation#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#5)]

    2. Fügen Sie der- `EndpointBehaviors` Eigenschaft [ \<des commonbehavior->](../../configure-apps/file-schema/wcf/commonbehaviors.md) Abschnitts das Behavior-Element hinzu, und Sperren Sie das-Element. (Um eine Bestätigung auf der Dienstseite zu installieren, muss die Bestätigung ein <xref:System.ServiceModel.Description.IServiceBehavior> sein und zur `ServiceBehaviors`-Eigenschaft hinzugefügt werden.) Das folgende Codebeispiel veranschaulicht die ordnungsgemäße Konfiguration nach den Schritten a. und b. Der einzige Unterschied ist, dass hier kein starker Name vergeben wird.

        [!code-csharp[LockdownValidation#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#6)]

    3. Speichern Sie die Datei machine.config. Das folgende Codebeispiel führt alle Aufgaben in Schritt 3 durch, speichert aber eine lokale Kopie der geänderten Datei machine.config.

        [!code-csharp[LockdownValidation#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#7)]

## <a name="example"></a>Beispiel

Das folgende Codebeispiel veranschaulicht, wie ein gemeinsames Verhalten zu einer machine.config-Datei hinzugefügt und wie eine Kopie auf der Festplatte gespeichert wird. Der `InternetClientValidatorBehavior` wird aus dem Beispiel zur [Sicherheits](../samples/security-validation.md) Überprüfung entnommen.

[!code-csharp[LockdownValidation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#1)]

## <a name="net-framework-security"></a>.NET Framework-Sicherheit

Sie können darüber hinaus die Elemente der Konfigurationsdatei verschlüsseln. Weitere Informationen finden Sie im Abschnitt "Siehe auch".

## <a name="see-also"></a>Siehe auch

- [Verschlüsseln von Konfigurationsdatei Elementen mit DPAPI](https://go.microsoft.com/fwlink/?LinkId=94954)
- [Verschlüsseln von Konfigurationsdatei Elementen mit RSA](https://go.microsoft.com/fwlink/?LinkId=94955)
