# LogStash Input Plugin for 1C Application Logs

[![Build Status](https://travis-ci.org/silverbulleters-research/logstash-vanessa-sqlitelogs.svg?branch=master)](https://travis-ci.org/silverbulleters-research/logstash-vanessa-sqlitelogs)

* ������ ��� ������ � ������� LogStash ������� ����������� � ������� sqlite ���  [��������� 1C:�����������](http://1c.ru) 

## ����������

��� �����������

* ������������ logstash
* ������� ������ �� �������� ������� [������� ����� 0.1.4](https://github.com/silverbulleters-research/logstash-vanessa-sqlitelogs/releases/download/0.1.4/logstash-input-sqliteonec-0.1.4.gem)
* ��������� ������� � ������� `logstash-plugin install /srv/logstash-input-sqliteonec-0.1.4.gem`

## ���������

* �������� ��� ���������������� ���� � �������� `input`, `filter` � `output`

��������� ������ `input` �������� ���

```
input {

    sqliteonec {
		type => "1CLog"
		path_since => "IncrementalInputTable" # ��� ������� ����� ��������� ������������������ ������
		onec_base_name => "MyVanessaERP" # ���������������� ��� ���� ��� �����������
		onec_base_guid => "9c1205e0-595b-4edd-9f70-6dda09b6f888" # GUID ���� (������ ������� �� ����� 1CV8Clst.lst)
		onec_server_reg_path => "C:\srvinfo\reg_1541" # ���� � �������� �������� �������� �� �������
    }

}
```

* ��������� `logstash -f your-config-file.conf` � ���� �� �������� ������� ���� kibana - �� ������ ���� ������� �����������

![simple logs](./docs/simple-discover.png)

## ���������� ���������

* ���������� JDK
* ���������� jruby
* `git clone` ��� ����� �����������
  * `git remote add myfork` ��� ������ �����
* ��������� `gem install bunder && bundle install
* �������� �������� � ������� RSspec (��� cucumber)
* ���������� [���� ��������](https://www.elastic.co/guide/en/logstash/5.0/_how_to_write_a_logstash_input_plugin.html#_how_to_write_a_logstash_input_plugin)
* �������� ������ ����� �����
* ��������� `bundle exec rspec spec`
* ��������� `bundle exec cucumber`
* ����������� `docker-run50-uat.sh` ��� ��������� �������� (��� `docker-run50-uat.cmd` ��� Windows 10 � ���������� docker � HyperV)
  * ���� ���������� ������ - ��������� `docker-logstash-only` ��� ������� � �����������
* ��������� �� ������ `http://localhost:5601` - �� ������� ������� ���� kibana c 2-�� ��������� ����������� 1� �� ���� ���
* ���� �� ������ � ��������� - �������� ���� pull-request ;-). ������ ���������� !!!

## ������ �� ���������� ��� � ������������ ?

* 1� ������ ��������� ��� !!!

## ������ �� Beats ���������� ?

�� ������, �� ����� ����� � ��� ����� �������

* ��� ���������� ����������� �������� Elastic Beats for 1C - https://github.com/silverbulleters/vanessa-beats
* � ���� ����������������� ����������� - https://github.com/silverbulleters-research/sqliteOneCBeat

������� �� ���������