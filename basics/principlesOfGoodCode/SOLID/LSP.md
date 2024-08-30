# The Liskov Substitution Principle

Принцип, при котором там, где приходят родительские классы без ошибок и падений, должны также без ошибок и падений приходить его наследники 

>Подкласс не должен требовать от вызывающего кода больше, чем базовый класс и не должен предоставлять вызывающему коду меньше, чем базовый класс.

Мы не должны тербовать от кода вызывающего класса, чтоб он знал о том, что вызывает конкретного child, из-за чего он должен использовать базовые методы по другим принципам

Мы не должны переопределять имеющеися методы так, чтобы совсем о них не было информации (возврат null, к примеру)