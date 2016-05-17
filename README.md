# Manala Nginx Autoindex Theme

## Integration

Clone the repository into a root hidden .theme folder

    git clone https://github.com/manala/nginx-autoindex-theme.git .theme

Add the following parameters to your nginx configuration

    ...
    add_before_body /.theme/header.html;
    add_after_body /.theme/footer.html;
    
    autoindex_exact_size off;
    autoindex on;
    ...

You can also handle subdirectoris this way

    location /foobar {
        alias /usr/share/nginx/html/foobar/;

        sub_filter_once off;
        sub_filter '/.theme' '/foobar/.theme';

        add_before_body /foobar/.theme/header.html;
        add_after_body /foobar/.theme/footer.html;

        autoindex_exact_size off;
        autoindex on;
    }

## Inspiration

https://github.com/tuxy/nginx-indexer
