# date.h
///Cabecera de la clase Fecha
#ifndef DATE_H_INCLUDED
#define DATE_H_INCLUDED
#include <time.h>
#include <cstdlib>
#include <cstdio>
#include <string>

class Date {
    private:
        int year;
        int month;
        int day;
    public:
        Date(); /// Constructor base
        Date(Date&); /// Constructor copia
        Date(const int&, const int&, const int&);/// Constructor parametrizado (año,mes,dia)

        bool isValidDate(const int&, const int&, const int&);///Validador de fecha (año,mes,dia)
        int toInt();///para imprimir los datos

        int getYear();
        int getMonth();
        int getDay();

        void setYear(const int&);
        void setMonth(const int&);
        void setDay(const int&);

        std::string toString();

        Date& operator = ( const Date&);
        bool operator == ( Date&);
        bool operator != ( Date&);
        bool operator < ( Date&);
        bool operator <= ( Date&);
        bool operator > ( Date&);
        bool operator >= ( Date&);

        friend std::ostream& operator << (std::ostream&, Date&);
        friend std::istream& operator >> (std::istream&, Date&);
    };

#endif // DATE_H_INCLUDED
