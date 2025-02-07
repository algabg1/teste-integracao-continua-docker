# 🐳 Testando CI/CD com GitHub Actions e Docker  

## 📌 Sobre o Projeto  
Este repositório tem como objetivo testar a configuração de uma **pipeline de integração contínua (CI/CD)** usando **GitHub Actions** e **Docker**. O processo inclui a construção e o envio de uma imagem Docker para o Docker Hub, garantindo que o código esteja sempre pronto para execução em ambientes conteinerizados.  

## O que é Integração Contínua (CI) e Entrega Contínua (CD)?  
- **Integração Contínua (CI)**: Automatiza a validação e os testes do código para evitar erros antes da implantação.  
- **Entrega Contínua (CD)**: Garante que novas versões do software possam ser implantadas de forma automatizada e consistente.  

Neste projeto, o **GitHub Actions** é usado para realizar esses processos de forma eficiente e integrada ao Docker.  

## Configuração da Pipeline  
O fluxo de trabalho está dividido em três etapas principais:  

1. **Testes (`Go.yml`)**  
   - O código é testado em diferentes versões do Go (`1.18`, `1.17`, `>=1.18`) e sistemas operacionais (`ubuntu-latest`, `ubuntu-20.04`).  
   - Um banco de dados PostgreSQL é iniciado via Docker Compose.  
   - Os testes são executados para validar o código.  

2. **Build (`Go.yml`)**  
   - Após os testes, o código-fonte é compilado.  
   - O artefato gerado (`main`) é armazenado para a próxima etapa.  

3. **Containerização e Deploy (`Docker.yml`)**  
   - O artefato compilado é baixado.  
   - A imagem Docker é construída e enviada para o **Docker Hub**.  

## Testes com Falhas no GitHub Actions  
Algumas **falhas foram inseridas propositalmente** para entender o comportamento do GitHub Actions, incluindo:  

- ❌ Testar com versões incompatíveis do Go.  
- ❌ Alterar a configuração do banco para quebrar a conexão.  
- ❌ Erros na autenticação do Docker Hub.  
- ❌ Problemas no `Dockerfile` para simular falhas de build.  

Esses experimentos ajudaram a compreender melhor o funcionamento das pipelines e a depuração de erros.  

## 📌 Conclusão  
Este projeto serviu como um estudo prático de **Integração e Entrega Contínua** usando **GitHub Actions e Docker**. A configuração permite validar, construir e distribuir a aplicação de forma automatizada, garantindo um fluxo de desenvolvimento mais eficiente.  

---

✍️ _Criado para aprendizado e testes com GitHub Actions e Docker_ 🐳
