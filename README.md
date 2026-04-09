# AWS WAF + CloudFront 構成

## 概要
AWS WAF を CloudFront に適用し、Webアプリケーションへの攻撃から
保護する構成を実装しました。

## アーキテクチャ
![構成図](aws-waf.png)

## 使用サービス
- AWS WAF（Web ACL）
- Amazon CloudFront
- AWS Managed Rules

## 適用したルール
- Core rule set（OWASPの一般的な脆弱性対策）
- Amazon IP reputation list（悪意のあるIPをブロック）

## 構成のポイント
- CloudFrontディストリビューションにWAFを紐付け
- マネージドルールにより追加コストなしで基本保護を実現
- ブロックされたリクエストはCloudWatchで確認可能
