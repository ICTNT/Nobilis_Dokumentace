---
vytvořeno: 2023-03-31T08:52
oddíl: "Nový zákazník EDI v money"
zdroj: "OneNote / Návody/EDI / Nový zákazník EDI v money"
tags:
  - onenote-import
  - k-revizi
---
- ⚠️ U Slovenských zákazníků (u nového) je potřeba zavést ho do transformační šablony:

\<xsl:if test="../../doc_header/party/party_ean = '8589000069849'"\>

        \<xsl:variable name="GLN" select="doc_header/party/party_ean" /\>

        \<xsl:element name="JednCena"\>

\<xsl:value-of select="utility:PriceSK(GLN, article_gtin, 1,2,3,4 )" /\>

\</xsl:element\>

\<xsl:element name="JednCenaCM"\>

\<xsl:value-of select="utility:PriceSK(GLN, article_gtin, 1,2,3,4 )" /\>

\</xsl:element\>

\<xsl:element name="JednotkovaPorizovaciCena"\>

\<xsl:value-of select="utility:PriceSK(GLN, article_gtin, 1,2,3,4 )" /\>

\</xsl:element\>

\</xsl:if\>
