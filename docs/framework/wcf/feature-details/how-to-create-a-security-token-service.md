---
title: 'Vorgehensweise: Erstellen eines Sicherheitstokendiensts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 98e82101-4cff-4bb8-a220-f7abed3556e5
author: BrucePerlerMS
ms.openlocfilehash: dd2c4f32978107a82ce940e0ef984c70f461b2c3
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2018
ms.locfileid: "47400040"
---
# <a name="how-to-create-a-security-token-service"></a><span data-ttu-id="230fc-102">Vorgehensweise: Erstellen eines Sicherheitstokendiensts</span><span class="sxs-lookup"><span data-stu-id="230fc-102">How to: Create a Security Token Service</span></span>
<span data-ttu-id="230fc-103">Ein Sicherheitstokendienst implementiert das in der WS-Trust-Spezifikation definierte Protokoll.</span><span class="sxs-lookup"><span data-stu-id="230fc-103">A security token service implements the protocol defined in the WS-Trust specification.</span></span> <span data-ttu-id="230fc-104">Dieses Protokoll definiert Meldungsformate und Meldungsaustauschmuster zum Herausgeben, Erneuern, Abbrechen und Überprüfen von Sicherheitstoken.</span><span class="sxs-lookup"><span data-stu-id="230fc-104">This protocol defines message formats and message exchange patterns for issuing, renewing, canceling, and validating security tokens.</span></span> <span data-ttu-id="230fc-105">Ein angegebener Sicherheitstokendienst stellt eine oder mehrere dieser Fähigkeiten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="230fc-105">A given security token service provides one or more of these capabilities.</span></span> <span data-ttu-id="230fc-106">Dieses Thema behandelt das am häufigsten verwendete Szenario: das Implementieren der Tokenausstellung.</span><span class="sxs-lookup"><span data-stu-id="230fc-106">This topic looks at the most common scenario: implementing token issuance.</span></span>  
  
## <a name="issuing-tokens"></a><span data-ttu-id="230fc-107">Ausstellen von Token</span><span class="sxs-lookup"><span data-stu-id="230fc-107">Issuing Tokens</span></span>  
 <span data-ttu-id="230fc-108">WS-Trust definiert Meldungsformate basierend auf dem `RequestSecurityToken`-XSD-Schemaelement (XML Schema Definition Language) und dem `RequestSecurityTokenResponse`-XSD-Schemaelement zum Durchführen der Tokenausstellung.</span><span class="sxs-lookup"><span data-stu-id="230fc-108">WS-Trust defines message formats, based on the `RequestSecurityToken` XML Schema definition language (XSD) schema element, and `RequestSecurityTokenResponse` XSD schema element for performing token issuance.</span></span> <span data-ttu-id="230fc-109">Außerdem definiert WS-Trust die zugeordneten Aktions-URIs (Action Uniform Resource Identifiers).</span><span class="sxs-lookup"><span data-stu-id="230fc-109">In addition, it defines the associated Action Uniform Resource Identifiers (URIs).</span></span> <span data-ttu-id="230fc-110">Aktions-URI mit der `RequestSecurityToken` Nachricht http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue.</span><span class="sxs-lookup"><span data-stu-id="230fc-110">The action URI associated with the `RequestSecurityToken` message is http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue.</span></span> <span data-ttu-id="230fc-111">Aktions-URI mit der `RequestSecurityTokenResponse` Nachricht http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue.</span><span class="sxs-lookup"><span data-stu-id="230fc-111">The action URI associated with the `RequestSecurityTokenResponse` message is   http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue.</span></span>  
  
### <a name="request-message-structure"></a><span data-ttu-id="230fc-112">Anforderungsmeldungsstruktur</span><span class="sxs-lookup"><span data-stu-id="230fc-112">Request Message Structure</span></span>  
 <span data-ttu-id="230fc-113">Die Anforderungsmeldungsstruktur für Probleme besteht normalerweise aus den folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="230fc-113">The issue request message structure typically consists of the following items:</span></span>  
  
-   <span data-ttu-id="230fc-114">Geben Sie eine Anforderung URI mit einem Wert von http://schemas.xmlsoap.org/ws/2005/02/trust/Issue.</span><span class="sxs-lookup"><span data-stu-id="230fc-114">A request type URI with a value of    http://schemas.xmlsoap.org/ws/2005/02/trust/Issue.</span></span>  
  
-   <span data-ttu-id="230fc-115">Ein Tokentyp-URI</span><span class="sxs-lookup"><span data-stu-id="230fc-115">A token type URI.</span></span> <span data-ttu-id="230fc-116">Für Security Assertions Markup Language (SAML) 1.1-Token ist der Wert dieses URIs http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1.</span><span class="sxs-lookup"><span data-stu-id="230fc-116">For Security Assertions Markup Language (SAML) 1.1 tokens, the value of this URI is http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1.</span></span>  
  
-   <span data-ttu-id="230fc-117">Ein Schlüsselgrößenwert, der die Anzahl der Bits im Schlüssel angibt, der dem ausgestellten Token zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="230fc-117">A key size value that indicates the number of bits in the key to be associated with the issued token.</span></span>  
  
-   <span data-ttu-id="230fc-118">Ein Schlüsseltyp-URI</span><span class="sxs-lookup"><span data-stu-id="230fc-118">A key type URI.</span></span> <span data-ttu-id="230fc-119">Für symmetrische Schlüssel ist der Wert dieses URIs http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="230fc-119">For symmetric keys, the value of this URI is http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey.</span></span>  
  
 <span data-ttu-id="230fc-120">Außerdem könnten ein paar andere Elemente vorhanden sein:</span><span class="sxs-lookup"><span data-stu-id="230fc-120">In addition, a couple of other items might be present:</span></span>  
  
-   <span data-ttu-id="230fc-121">Schlüsselmaterial, das vom Client bereitgestellt wird</span><span class="sxs-lookup"><span data-stu-id="230fc-121">Key material provided by the client.</span></span>  
  
-   <span data-ttu-id="230fc-122">Umfangsinformationen, die den Zieldienst angeben, mit dem das ausgestellte Token verwendet wird</span><span class="sxs-lookup"><span data-stu-id="230fc-122">Scope information that indicates the target service that the issued token will be used with.</span></span>  
  
 <span data-ttu-id="230fc-123">Der Sicherheitstokendienst verwendet die Informationen in der Problemanforderungsmeldung für die Erstellung der Problemantwortmeldung.</span><span class="sxs-lookup"><span data-stu-id="230fc-123">The security token service uses the information in the issue request message when it constructs the Issue Response message.</span></span>  
  
## <a name="response-message-structure"></a><span data-ttu-id="230fc-124">Antwortmeldungsstruktur</span><span class="sxs-lookup"><span data-stu-id="230fc-124">Response Message Structure</span></span>  
 <span data-ttu-id="230fc-125">Die Antwortmeldungsstruktur für Probleme besteht normalerweise aus den folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="230fc-125">The issue response message structure typically consists of the following items;</span></span>  
  
-   <span data-ttu-id="230fc-126">dem ausgestellten Sicherheitstoken, z. B. eine SAML 1.1-Assertion</span><span class="sxs-lookup"><span data-stu-id="230fc-126">The issued security token, for example, a SAML 1.1 assertion.</span></span>  
  
-   <span data-ttu-id="230fc-127">einem dem Sicherheitstoken zugeordnete Prüftoken.</span><span class="sxs-lookup"><span data-stu-id="230fc-127">A proof token associated with the security token.</span></span> <span data-ttu-id="230fc-128">Für symmetrische Schlüssel ist dies oft eine verschlüsselte Form des Schlüsselmaterials.</span><span class="sxs-lookup"><span data-stu-id="230fc-128">For symmetric keys, this is often an encrypted form of the key material.</span></span>  
  
-   <span data-ttu-id="230fc-129">Verweise auf das ausgestellte Sicherheitstoken</span><span class="sxs-lookup"><span data-stu-id="230fc-129">References to the issued security token.</span></span> <span data-ttu-id="230fc-130">Der Sicherheitstokendienst gibt normalerweise einen Verweis zurück, der verwendet werden kann, wenn das ausgestellte Token in einer vom Client gesendeten nachfolgenden Meldung angezeigt wird, und einen Verweis, der verwendet werden kann, wenn das Token in nachfolgenden Meldungen nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="230fc-130">Typically, the security token service returns a reference that can be used when the issued token appears in a subsequent message sent by the client and another that can be used when the token is not present in subsequent messages.</span></span>  
  
 <span data-ttu-id="230fc-131">Außerdem könnten ein paar andere Elemente vorhanden sein:</span><span class="sxs-lookup"><span data-stu-id="230fc-131">In addition, a couple of other items might be present:</span></span>  
  
-   <span data-ttu-id="230fc-132">Vom Sicherheitstokendienst bereitgestelltes Schlüsselmaterial</span><span class="sxs-lookup"><span data-stu-id="230fc-132">Key material provided by the security token service.</span></span>  
  
-   <span data-ttu-id="230fc-133">Der zum Berechnen des freigegebenen Schlüssels benötigte Algorithmus</span><span class="sxs-lookup"><span data-stu-id="230fc-133">The algorithm needed to compute the shared key.</span></span>  
  
-   <span data-ttu-id="230fc-134">Lebensdauerinformationen für das ausgestellte Token.</span><span class="sxs-lookup"><span data-stu-id="230fc-134">Lifetime information for the issued token.</span></span>  
  
## <a name="processing-request-messages"></a><span data-ttu-id="230fc-135">Verarbeiten von Anforderungsmeldungen</span><span class="sxs-lookup"><span data-stu-id="230fc-135">Processing Request Messages</span></span>  
 <span data-ttu-id="230fc-136">Der Sicherheitstokendienst verarbeitet die Problemanforderung durch Untersuchen der verschiedenen Teile der Anforderungsmeldung und durch Sicherstellen der Ausstellung eines Tokens, das der Anforderung entspricht.</span><span class="sxs-lookup"><span data-stu-id="230fc-136">The security token service processes the issue request by examining the various pieces of the request message and ensuring that it can issue a token that satisfies the request.</span></span> <span data-ttu-id="230fc-137">Der Sicherheitstokendienst muss Folgendes bestimmen, bevor er das auszustellende Token erstellt:</span><span class="sxs-lookup"><span data-stu-id="230fc-137">The security token service must determine the following before it constructs the token to be issued:</span></span>  
  
-   <span data-ttu-id="230fc-138">Die Anforderung ist tatsächlich eine Anforderung für ein auszustellendes Token.</span><span class="sxs-lookup"><span data-stu-id="230fc-138">The request really is a request for a token to be issued.</span></span>  
  
-   <span data-ttu-id="230fc-139">Der Sicherheitstokendienst unterstützt den angeforderten Tokentyp.</span><span class="sxs-lookup"><span data-stu-id="230fc-139">The security token service supports the requested token type.</span></span>  
  
-   <span data-ttu-id="230fc-140">Der Anforderungsdienst wird zum Erstellen der Anforderungen autorisiert.</span><span class="sxs-lookup"><span data-stu-id="230fc-140">The requester is authorized to make the request.</span></span>  
  
-   <span data-ttu-id="230fc-141">Der Sicherheitstokendienst kann den Erwartungen des Anforderungsdiensts in Bezug auf das Schlüsselmaterial entsprechen.</span><span class="sxs-lookup"><span data-stu-id="230fc-141">The security token service can meet the requester's expectations with respect to key material.</span></span>  
  
 <span data-ttu-id="230fc-142">Zwei wichtige Teile beim Erstellen eines Tokens bestehen im Bestimmen des Schlüssels, mit dem das Token signiert werden soll, und des Schlüssels, mit dem der freigegebene Schlüssel verschlüsselt werden soll.</span><span class="sxs-lookup"><span data-stu-id="230fc-142">Two vital parts of constructing a token are determining what key to sign the token with and what key to encrypt the shared key with.</span></span> <span data-ttu-id="230fc-143">Das Token muss signiert werden, damit der Dienst ermitteln kann, ob das Token von einem Sicherheitstokendienst ausgestellt wurde, dem er vertraut, wenn der Client dem Zieldienst das Token bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="230fc-143">The token needs to be signed so that when the client presents the token to the target service, that service can determine that the token was issued by a security token service that it trusts.</span></span> <span data-ttu-id="230fc-144">Das Schlüsselmaterial muss in einer Art und Weise verschlüsselt werden, dass der Zieldienst das Schlüsselmaterial entschlüsseln kann.</span><span class="sxs-lookup"><span data-stu-id="230fc-144">The key material needs to be encrypted in such a way that the target service can decrypt that key material.</span></span>  
  
 <span data-ttu-id="230fc-145">Das Signieren einer SAML-Assertion schließt das Erstellen einer <xref:System.IdentityModel.Tokens.SigningCredentials>-Instanz ein.</span><span class="sxs-lookup"><span data-stu-id="230fc-145">Signing a SAML assertion involves creating a <xref:System.IdentityModel.Tokens.SigningCredentials> instance.</span></span> <span data-ttu-id="230fc-146">Der Konstruktor für diese Klasse kann Folgendes sein:</span><span class="sxs-lookup"><span data-stu-id="230fc-146">The constructor for this class takes the following:</span></span>  
  
-   <span data-ttu-id="230fc-147">Ein <xref:System.IdentityModel.Tokens.SecurityKey> für den Schlüssel zum Signieren der SAML-Assertion</span><span class="sxs-lookup"><span data-stu-id="230fc-147">A <xref:System.IdentityModel.Tokens.SecurityKey> for the key to use to sign the SAML assertion.</span></span>  
  
-   <span data-ttu-id="230fc-148">Eine Zeichenfolge, die den zu verwendenden Signaturalgorithmus identifiziert</span><span class="sxs-lookup"><span data-stu-id="230fc-148">A string identifying the signature algorithm to use.</span></span>  
  
-   <span data-ttu-id="230fc-149">Eine Zeichenfolge, die den zu verwendenden Hashwertalgorithmus identifiziert</span><span class="sxs-lookup"><span data-stu-id="230fc-149">A string identifying the digest algorithm to use.</span></span>  
  
-   <span data-ttu-id="230fc-150">Optional ein <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier>, der den Schlüssel identifiziert, der zum Signieren der Assertion verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="230fc-150">Optionally, a <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> that identifies the key to use to sign the assertion.</span></span>  
  
 [!code-csharp[c_CreateSTS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#1)]
 [!code-vb[c_CreateSTS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#1)]  
  
 <span data-ttu-id="230fc-151">Das Verschlüsseln des freigegebenen Schlüssels schließt das Verschlüsseln des Schlüsselmaterials mit einem Schlüssel ein, den der Zieldienst zum Entschlüsseln des freigegeben Schlüssels verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="230fc-151">Encrypting the shared key involves taking the key material and encrypting it with a key that the target service can use to decrypt the shared key.</span></span> <span data-ttu-id="230fc-152">Normalerweise wird der öffentliche Schlüssel des Zieldiensts verwendet.</span><span class="sxs-lookup"><span data-stu-id="230fc-152">Typically, the public key of the target service is used.</span></span>  
  
 [!code-csharp[c_CreateSTS#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#2)]
 [!code-vb[c_CreateSTS#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#2)]  
  
 <span data-ttu-id="230fc-153">Außerdem wird ein <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> für den verschlüsselten Schlüssel benötigt.</span><span class="sxs-lookup"><span data-stu-id="230fc-153">In addition, a <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> for the encrypted key is needed.</span></span>  
  
 [!code-csharp[c_CreateSTS#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#3)]
 [!code-vb[c_CreateSTS#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#3)]  
  
 <span data-ttu-id="230fc-154">Dieser <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> wird dann zum Erstellen eines `SamlSubject` als Teil des `SamlToken` verwendet.</span><span class="sxs-lookup"><span data-stu-id="230fc-154">This <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> is then used to create a `SamlSubject` as part of the `SamlToken`.</span></span>  
  
 [!code-csharp[c_CreateSTS#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#4)]
 [!code-vb[c_CreateSTS#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#4)]  
  
 <span data-ttu-id="230fc-155">Weitere Informationen finden Sie unter [Verbundbeispiel](../../../../docs/framework/wcf/samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="230fc-155">For more information, see [Federation Sample](../../../../docs/framework/wcf/samples/federation-sample.md).</span></span>  
  
## <a name="creating-response-messages"></a><span data-ttu-id="230fc-156">Erstellen von Antwortmeldungen</span><span class="sxs-lookup"><span data-stu-id="230fc-156">Creating Response Messages</span></span>  
 <span data-ttu-id="230fc-157">Sobald der Sicherheitstokendienst die Problemanforderung verarbeitet und das auszustellende Token zusammen mit dem Prüfschlüssel erstellt, muss die Antwortmeldung erstellt werden, die mindestens das angeforderte Token, das Prüftoken und die ausgestellten Tokenverweise enthalten muss.</span><span class="sxs-lookup"><span data-stu-id="230fc-157">Once the security token service processes the issue request and constructs the token to be issued along with the proof key, the response message needs to be constructed, including at least the requested token, the proof token, and the issued token references.</span></span> <span data-ttu-id="230fc-158">Das ausgestellte Token ist normalerweise ein aus der <xref:System.IdentityModel.Tokens.SamlSecurityToken> erstelltes <xref:System.IdentityModel.Tokens.SamlAssertion>, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="230fc-158">The issued token is typically a <xref:System.IdentityModel.Tokens.SamlSecurityToken> created from the <xref:System.IdentityModel.Tokens.SamlAssertion>, as shown in the following example.</span></span>  
  
 [!code-csharp[c_CreateSTS#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#5)]
 [!code-vb[c_CreateSTS#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#5)]  
  
 <span data-ttu-id="230fc-159">Wenn der Sicherheitstokendienst das freigegebene Schlüsselmaterial bereitstellt, wird das Prüftoken durch Erstellen eines <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken> erstellt.</span><span class="sxs-lookup"><span data-stu-id="230fc-159">In the case where the security token service provides the shared key material, the proof token is constructed by creating a <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>.</span></span>  
  
 [!code-csharp[c_CreateSTS#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#6)]
 [!code-vb[c_CreateSTS#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#6)]  
  
 <span data-ttu-id="230fc-160">Weitere Informationen zum Erstellen des prüftokens, wenn sowohl der Client als auch dem Sicherheitstokendienst Schlüsselmaterial für den gemeinsam verwendeten Schlüssel bereitstellt, finden Sie unter [Verbundbeispiel](../../../../docs/framework/wcf/samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="230fc-160">For more information about how to construct the proof token when the client and the security token service both provide key material for the shared key, see [Federation Sample](../../../../docs/framework/wcf/samples/federation-sample.md).</span></span>  
  
 <span data-ttu-id="230fc-161">Die ausgestellten Tokenverweise werden durch Erstellen von Instanzen der <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause>-Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="230fc-161">The issued token references are constructed by creating instances of the <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause> class.</span></span>  
  
 [!code-csharp[c_CreateSTS#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#7)]
 [!code-vb[c_CreateSTS#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#7)]  
  
 <span data-ttu-id="230fc-162">Diese verschiedenen Werte werden dann in der Antwortmeldung, die an den Client zurückgegeben wird, serialisiert.</span><span class="sxs-lookup"><span data-stu-id="230fc-162">These various values are then serialized into the response message returned to the client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="230fc-163">Beispiel</span><span class="sxs-lookup"><span data-stu-id="230fc-163">Example</span></span>  
 <span data-ttu-id="230fc-164">Vollständiger Code für einen Security token Service, finden Sie unter [Verbundbeispiel](../../../../docs/framework/wcf/samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="230fc-164">For full code for a security token service, see [Federation Sample](../../../../docs/framework/wcf/samples/federation-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="230fc-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="230fc-165">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SigningCredentials>  
 <xref:System.IdentityModel.Tokens.SecurityKey>  
 <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier>  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
 <xref:System.IdentityModel.Tokens.SamlAssertion>  
 <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>  
 <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause>  
 [<span data-ttu-id="230fc-166">Verbundbeispiel</span><span class="sxs-lookup"><span data-stu-id="230fc-166">Federation Sample</span></span>](../../../../docs/framework/wcf/samples/federation-sample.md)
